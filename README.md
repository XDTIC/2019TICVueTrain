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

4. Introduce：hello-vue

> You need to install an extra plugin：`npm install -g @vue/cli-service-global`

Create File `/hello-world/HelloVue.vue`:
```
<template>
  <h1>Hello Vue!</h1>
</template>
```

Shell: `vue serve /hello-world/HelloVue.vue`

@See your work: <a href="http://localhost:8080">http://localhost:8080</a>

## Practice

Compelete An Vue-Component Like this:

![](/.github/logintrace.png)

> @See `/login-trace/LoginTrace.vue`
> Use: `vue serve ./login-trace/LoginTrace.vue` to preview the example.

- When mouse hover on any login-trace-block, it should pop-out the date string.
- When AJAX is not finished, you need set a loading info.
- Module every login-trace-block.

Documents you may need:

- `title`:[https://www.w3school.com.cn/tags/att_standard_title.asp](https://www.w3school.com.cn/tags/att_standard_title.asp)
- `v-if`:[https://cn.vuejs.org/v2/guide/conditional.html](https://cn.vuejs.org/v2/guide/conditional.html)
- `v-for`:[https://cn.vuejs.org/v2/guide/list.html](https://cn.vuejs.org/v2/guide/list.html)
- `vue-component`:[https://cn.vuejs.org/v2/guide/components-registration.html](https://cn.vuejs.org/v2/guide/components-registration.html)
- `props`:[https://cn.vuejs.org/v2/guide/components-registration.html](https://cn.vuejs.org/v2/guide/components-registration.html)
- `v-bind`:[https://cn.vuejs.org/v2/guide/class-and-style.html](https://cn.vuejs.org/v2/guide/class-and-style.html)
- `computed`:[https://cn.vuejs.org/v2/guide/computed.html](https://cn.vuejs.org/v2/guide/computed.html)

There is a demo here: [/login-trace/LoginTrace.vue](/login-trace/LoginTrace.vue)