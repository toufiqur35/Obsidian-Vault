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