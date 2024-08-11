Up to this point, we have just been using one page/url with all of our components. In a real application, we would have multiple pages and we would need to navigate between them. This is where Vue Router comes in. Vue Router is the official router for Vue.js. We need the router because we will have a separate page for jobs and single job listings as well as the page to add and update listings. You could have chosen to implement the router at the very beginning, but I wanted to show you how to do it yourself.

Let's install Vue Router:

```
npm install vue-router
```

Now we need to set up the router. Create a file at `src/router/index.js` and add the following:

```js
import { createRouter, createWebHistory } from 'vue-router';
import HomeView from '@/views/HomeView.vue';

const router = createRouter({
  history: createWebHistory(),
  routes: [
    {
      path: '/',
      name: 'home',
      component: HomeView,
    },
  ],
});

export default router;
```

Now let's open up the `src/main.js` file and apply the router:

```js
import { createApp } from 'vue';
import App from './App.vue';
import router from './router';

const app = createApp(App);
app.use(router);
app.mount('#app');
```

We have imported the router and then we are using it in the `createApp` function. Now we can use the router in our components.

```html
<RouterLink to='/'> Home </RouterLink>
```

## Active Links

The routing should work, however, the active link is always the home link. We need to add some logic to make sure the active link is the current page.

Let's bring in `useRoute` from the `vue-router` package:

```
import { RouterLink, useRoute } from 'vue-router';
```

Now add the following function:

```html
<script setup>
  import { RouterLink, useRoute } from 'vue-router';
  const isActiveLink = (routePath) =>{
    return useRoute().path === routePath;
  }
</script>

<template>
<RouterLink to="/" :class="[isActiveLink('/')? 'bg-green-900' : '', 'text-white hover:bg-gray-900 hover:text-white rounded-md px-3 py-2']">Home</RouterLink>
</template>
```