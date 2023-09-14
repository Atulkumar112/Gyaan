# Vue.js Framework

## Diff b/w v-bind and v-model
Both are use for data binding, but v-bind use for one-way data binding whereas v-model is use for two-way data binding.
v-bind is used for one-way data binding, where you bind an element's attribute or property to a value or expression. v-model, on the other hand, is used for two-way data binding, specifically designed for form inputs, to automatically sync the data between the input and the Vue component.
Example of v-bind
```bash
<template>
  <a v-bind:href="url">Visit OpenAI</a>
</template>

<script>
export default {
  data() {
    return {
      url: 'https://openai.com',
    };
  },
};
</script>
```

Example of v-model
```bash
<template>
  <input v-model="message" type="text">
  <p>Message: {{ message }}</p>
</template>

<script>
export default {
  data() {
    return {
      message: '',
    };
  },
};
</script>
```


## What are Vue.js directives? 
Directives are used to manipulate the behavior or appearance of DOM elements. v-if, v-else, v-model, v-bind, v-show, v-on(or shorthand is @), v-for these all are the vue directives.


## What is the v-on?
In vue, v-on is a directive used for event handling. It allows you to attach event listeners to HTML elements and execute methods or code when the events occur. The v-on directive can be used in two different ways: as a shorthand with the @ symbol or with the full v-on syntax.

## What is the router in vue.js
Vue Router is the official routing library for Vue.js. It provides a way to handle client-side navigation and build single-page applications (SPAs) with multiple views. Vue Router allows you to define routes, map them to corresponding components, and perform dynamic navigation between them.

## What is v-if and v-show.
- v-show: -v-show is a directive that toggles the visibility of an element by adding or removing the display: none CSS property. The element always remains in the DOM, and its CSS properties are modified to hide or show it.

- v-if:- On the other hand, v-if is a directive that conditionally renders an element based on the truthiness of the expression. If the expression is truthy, the element is rendered and added to the DOM. If the expression is falsy, the element is not rendered and not included in the DOM.

## How can you communicate between components in Vue.js?
Vue.js provides various ways to communicate between components, such as props (parent-to-child communication), events (child-to-parent communication), and a centralized event bus or state management pattern like Vuex.

## What is the hooks and life cycle of vue.js
These are majar 8 types of hooks life cycle which are followings...
1. beforeCreate: This hook is called before the instance is created. The data and methods are not accessible yet. OR This hook is called before the instance is created, and data observation and event initialization have not occurred yet. Generally, you won't use this hook very often.
2. created: This hook is called after the instance is created. The data and methods are accessible, but the DOM has not been mounted yet. OR This hook is called after the instance is created. The component has access to its data and can perform additional setup tasks like making API calls, initializing external libraries, or setting up event listeners. example:- when you need to fetch the data form the API.
3. beforeMount: This hook is called before the instance is mounted to the DOM. OR This hook is called before the component is mounted to the DOM. You can use this hook to make any necessary preparations or manipulations to the component or its child components.
4. mounted: This hook is called after the instance is mounted to the DOM. OR This hook is called when the component is successfully mounted to the DOM. It is often used for initialization tasks that require access to the DOM, such as fetching data from an API or setting up third-party libraries.example:- Initializing Third-Party Libraries.
5. beforeUpdate: This hook is called before a data change causes a re-render of the component. The updated data is accessible. OR This hook is called when a reactive property used by the component changes, before the virtual DOM is re-rendered. It allows you to perform some actions or make calculations before the update takes place.
6. updated: This hook is called after a data change causes a re-render of the component. OR This hook is called after the component's virtual DOM has been re-rendered due to a reactive property change. It's useful for performing actions that need to happen after an update, such as interacting with the updated DOM or making API calls based on updated data.
7. beforeUnmount(in vue3 version) or beforeDestroy(in vue2 version): This hook is called before the instance is destroyed. The instance is still fully functional. OR This hook is called when the component is about to be unmounted from the DOM. You can perform any necessary cleanup tasks or unsubscribe from event listeners in this hook.
8. unmounted(in vue3 version) or destroyed (in vue2 version): This hook is called after the instance is destroyed. The instance and its data are no longer accessible. This hook is called after the component has been unmounted from the DOM. It allows you to perform any final cleanup tasks or perform additional actions before the component is destroyed.
- Extra hook is:---------
9. errorCaptured: This hook is called when an error is thrown in any child component. It receives the error and the component instance.


## What is the components in vue.js
Components are reusable and self-contained UI elements with their own templates, logic, and data. 

## What is the computed property in vue.js
Computed properties allow us to transform or perform calculations on our data and then easily reuse the result as an up-to-date variable in our template. or Computed properties in Vue.js are used to reduce complex or blotted logic that we write in our template

