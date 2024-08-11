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
  history: createWebHistory(import.meta.env.BASE_URL),
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