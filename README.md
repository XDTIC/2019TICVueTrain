# 2019TIC vue 入门培训

## Outline

1. What is MVVM? And differences with MVC.

We don't even care about the dom-tree. See examples below:

With JQuery or Origin-JS:
```
<p id="name">TIC</p>
-------------
$('#name').text('XDTIC');
document.getElementById('name').innerHTML = 'XDTIC';
```

Now, with Vue.js:
```
<p>{{name}}</p>
-------------
app.name = 'XDTIC';
```


2. How it work?

> @see `/hello-world/Calculator.vue`

3. Tools we need and what is vue-cli

Install **vue-cli**: `npm install -g @vue/cli`

4. hello-vue

> You need to install an extra plugin：`npm install -g @vue/cli-service-global`

Create File `/hello-world/HelloVue.vue`:
```
<template>
  <h1>Hello Vue!</h1>
</template>
```

Shell: `vue serve /hello-world/HelloVue.vue`

@See your work: <a href="http://localhost:8080">http://localhost:8080</a>


