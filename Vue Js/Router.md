src/router/index.js

```js
import { createRouter, createWebHistory } from 'vue-router';
import HomeView from '@/views/HomeView.vue';
import JobsView from '@/views/JobsView.vue';

const router = createRouter({
  history: createWebHistory(import.meta.env.BASE_URL),
  routes: [
    {
      path: '/',
      name: 'home',
      component: HomeView,
    },
    {
      path: '/jobs',
      name: 'jobs',
      component: JobsView,
    },
  ],
});
export default router;
```

src/main.js

```js
import router from './router';
import { createApp } from 'vue';
import App from './App.vue';
const app = createApp(App)
app.use(router);
app.mount('#app');
```