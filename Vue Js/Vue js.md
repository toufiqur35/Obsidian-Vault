### What is Vue Js?
* Progressive javaScript framework for building user interfaces & SPAs.
* Designed to be simple, flexible and incrementally adoptable.
* Used for projects of all sixes.
* Reactive data binding & component based architecture.
## Why Vue?
##### 1. Progressive Framework
Vue.js is a progressive framework, which means you can adopt it incrementally. You can start using it for a small part of your application and expand its use as needed.
##### 2. Lightweight and Fast
Vue.js is a lightweight framework, which contributes to its fast performance. The size of the framework is smaller compared to other major frameworks like React and Angular, leading to quicker load times and better user experience.
##### 3. Easy to Learn
Vue.js has a gentle learning curve. Its documentation is comprehensive and well-organized, making it accessible for beginners. The framework follows an intuitive approach, and developers who are familiar with HTML, CSS, and JavaScript can quickly get up to speed.
##### 4. Reactivity System
Vue.js features a powerful reactivity system that automatically updates the DOM when the underlying data changes. This helps in building dynamic user interfaces with less manual manipulation of the DOM, leading to cleaner and more maintainable code.
##### 5. Component-Based Architecture
Vue.js uses a component-based architecture, which allows you to break down the user interface into reusable components. This modularity improves code organization, maintenance, and collaboration among developers.
##### 6. Flexibility
Vue.js can be used for both small and large-scale applications. It offers flexibility in how you structure your application, whether you prefer a traditional monolithic approach or a more modern, modular architecture using Vuex for state management and Vue Router for routing.
##### 7. Integration Capabilities
Vue.js can be easily integrated with other libraries or existing projects. It plays well with other technologies, making it a suitable choice for adding interactivity to server-rendered or static applications.
##### 8. Strong Community and Ecosystem
Vue.js has a vibrant and supportive community. The ecosystem includes a variety of official and third-party libraries, tools, and plugins, which can accelerate development and provide solutions to common problems.
##### 9. Server-Side Rendering (SSR)
Vue.js supports server-side rendering (SSR), which can improve the performance and SEO of your application. SSR allows you to pre-render the initial state of your application on the server, reducing the time to first contentful paint and providing a better experience for users.
##### 10. Custom Directives and Templates
Vue.js offers the ability to create custom directives and templates, providing developers with greater control over the structure and behavior of their components.
##### 11. Excellent Documentation
The official Vue.js documentation is widely regarded as one of the best in the industry. It provides clear, concise, and detailed explanations of the framework's features and best practices, making it easy for developers to find the information they need.
##### 12. Two-Way Data Binding
Vue.js provides two-way data binding, which allows for automatic synchronization of data between the model and the view. This simplifies the process of keeping the UI and data model in sync, reducing the amount of boilerplate code needed.
##### 13. Versatility in Use Cases
Vue.js is suitable for a wide range of applications, from small widgets and single-page applications (SPAs) to large-scale, complex projects. Its versatility makes it a popular choice for developers working on various types of projects.
##### 14. Efficient and Scalable
Vue.js is designed to be both efficient and scalable, making it a good choice for projects of any size. Its component-based architecture and efficient reactivity system help maintain performance even as your application grows.

### Create-Vue

Open a terminal window and run the following:

```
npm create vue@latest project-name
```

I am going to choose the following options:
- TypeScript: no
- JSX: no
- Vue Router:  no
- Pinia: no
- Vitest: no
- End to End Testing: no
- ESLint: no
- DevTools: no
- 
Open this folder in VS Code or whatever editor you are using.

```
cd project-name
code .
```

Install & Run the Development Server:

```
npm install 
npm run dev
```
### Vue Components

* Reusable, self-contained pieces of code.
* Include the logic/js dynamic HTML output & scoped styling.
* Option API vs Composition API.
Here is an example of how Vue components are formatted and structured:

``` vue
<script>
// Vue component definition
export default {
  name: 'Simple Component',
};
</script>

<template>
  <div>
    <h2>Hello from Vue.js!</h2>
    <p>{{ name }}</p>
  </div>
</template>

<style scoped>
/* Scoped CSS for this component */
	h2 {
	  color: #333;
	}
	p {
	  font-size: 16px;
	  line-height: 1.6;
	}
</style>
```

## Directive
- `v-if` - Render the element if the expression is true. There is also `v-else` and `v-else-if`.
- `v-for` - Iterate over an array of items and render them.
- `v-bind` - Bind an attribute to a property on the component.
- `v-on` - Bind an event to a function.
- `v-model` - Bind an input to a property on the component.
- `v-show` - Show or hide an element based on the expression.
### v-if
Let's look at an example of using the `v-if` directive. First we will add a new piece of data to the component. Add the following to the script tag:

```vue
<script>
export default {
  data() {
    return {
      name: 'John Doe',
      status: 'active',
    };
  },
};
</script>
```

Now we can use the `v-if` directive to conditionally render the status. Add the following under the name:

```html
<h1>{{ name }}</h1>
<p v-if="status === 'active'">User is active</p>
```
### v-else
You can also use `v-else` to show something else if the condition is false. Add the following to the template:

```html
<h1>{{ name }}</h1>
<p v-if="status === 'active'">User is active</p>
<p v-else>User is Inactive</p>
```

Now it will show that the user is inactive if the `status` is set to something else.

### v-else-if
You can also use `v-else-if` to add another condition:

```html
<h1>{{ name }}</h1>
<p v-if="status === 'active'">User is Active</p>
<p v-else-if="status === 'pending'">User is Pending</p>
<p v-else>User is Inactive</p>
```

Now it will show active if active, pending if pending and inactive if anything else.

### v-for
You can also use `v-for` to iterate over an array of items. Let's add an array of tasks to the data:

```vue
<script>
export default {
  data() {
    return {
      name: 'John Doe',
      status: 'active',
      tasks: ['Task One', 'Task Two', 'Task Three', 'Task Four'],
    };
  },
};
</script>
```

Now we can use `v-for` to loop over the tasks:

```html
<h3>Tasks:</h3>
<ul>
  <li v-for="task in tasks" :key="task">{{ task }}</li>
</ul>
```

The `v-for` directive takes the form of `v-for="item in items"`. The `:key` attribute is required when using `v-for` to help Vue keep track of the elements and their state. You should now see the tasks on the page.

### v-bind
The `v-bind` directive is used to bind an attribute to a property on the component. For example, you can bind the `href` attribute of an anchor tag to a property on the component. Let's add a link to the data:

```vue
<script>
export default {
  data() {
    return {
      name: 'John Doe',
      status: 'active',
      tasks: ['Task One', 'Task Two', 'Task Three', 'Task Four'],
      link: 'https://google.com',
    };
  },
};
</script>
```

Now we can bind the `href` attribute of an anchor tag to the `link` property:

```html
<a v-bind:href="link">Link to Google</a>
```

We can also shorten this to `:href`:

```html
<a :href="link">Link to Google</a>
```

### `v-on` & Methods

The `v-on` directive is used to bind an event to a function/method. For example, you can bind a click event to a function that changes the status. Let's do that.

First, add the button with the following:

```html
<button
  v-on:click='toggleStatus'
  class='mt-3 px-4 py-2 bg-blue-500 text-white rounded-md'>
  Change Status
</button>

//v-on Shorthand
<button
  @click='toggleStatus'
  class='mt-3 px-4 py-2 bg-blue-500 text-white rounded-md'>
  Change Status
</button>
```

This will fire off a click event when the button is clicked. Now let's add the method to the data. Remember, we are still using the Options API. I will convert it to the Composition API soon:

```vue
<script>
export default {
  data() {
    return {
      status: 'active',
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pending';
      } else if (this.status === 'pending') {
        this.status = 'inactive';
      } else {
        this.status = 'active';
      }
    },
  },
};
</script>
```

## Lifecycle Hooks

In Vue, we have something called lifecycle hooks. These are functions that are called at different points in the lifecycle of a component. For example, when the component is created, mounted, updated, and destroyed. We can use these hooks to perform actions at these different points. There are a couple of them that were actually removed in Vue 3 because they were replaced by the setup() function, but the main ones are:

- `onBeforeMount` – called before mounting begins
- `onMounted` – called when component is mounted
- `onBeforeUpdate` – called when reactive data changes and before re-render
- `onUpdated` – called after re-render
- `onBeforeUnmount` – called before the Vue instance is destroyed
- `onUnmounted` – called after the instance is destroyed
- `onActivated` – called when a kept-alive component is activated
- `onDeactivated` – called when a kept-alive component is deactivated
- `onErrorCaptured` – called when an error is captured from a child component

### Detailed Explanation of Each Lifecycle Hook

#### 1. `beforeCreate`
- **When it’s called**: Before the component instance is initialized.
- **What you can do**: Access component options but not `data`, `computed`, or `methods` because the instance is not fully created yet.
#### 2. `created`
- **When it’s called**: After the component instance is created and the reactive properties are set up.
- **What you can do**: Access reactive data, computed properties, and methods. Useful for initializing data that depends on props or external sources.
#### 3. `beforeMount`
- **When it’s called**: Before the component is mounted to the DOM.
- **What you can do**: Access reactive data but not the DOM elements. Typically used to make last-minute changes before the initial render.
#### 4. `mounted`

- **When it’s called**: After the component is mounted to the DOM.
- **What you can do**: Access reactive data and the DOM. Ideal for making AJAX requests, setting up event listeners, or initializing third-party libraries that require a DOM element.
#### 5. `beforeUpdate`
- **When it’s called**: Before the component updates, right before the DOM is patched.
- **What you can do**: Access the current state of data and DOM before the update.
#### 6. `updated`
- **When it’s called**: After the component updates and the DOM is patched.
- **What you can do**: Access the updated state of data and DOM. Be cautious not to trigger additional updates in this hook, which could lead to an infinite loop.
#### 7. `beforeUnmount`
- **When it’s called**: Before the component is unmounted and removed from the DOM.
- **What you can do**: Perform cleanup operations like removing event listeners, canceling network requests, or stopping timers.
#### 8. `unmounted`
- **When it’s called**: After the component is unmounted and removed from the DOM.
- **What you can do**: Final cleanup operations.
#### Using Lifecycle Hooks in the `setup` Function

When using the Composition API, lifecycle hooks are available as functions that can be imported from Vue.

```vue
<template>
  <div>
    <h1>{{ title }}</h1>
    <button @click="updateTitle">Update Title</button>
  </div>
</template>

<script>
import { ref, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue';

export default {
  setup() {
    const title = ref('Hello, Vue!');
    const updateTitle = () => {
      title.value = 'Updated Title!';
    };

    onMounted(() => {
      console.log('Component has been mounted');
    });

    onBeforeUpdate(() => {
      console.log('Component is about to be updated');
    });

    onUpdated(() => {
      console.log('Component has been updated');
    });

    onBeforeUnmount(() => {
      console.log('Component is about to be unmounted');
    });

    onUnmounted(() => {
      console.log('Component has been unmounted');
    });

    return {
      title,
      updateTitle,
    };
  },
};
</script>

```

