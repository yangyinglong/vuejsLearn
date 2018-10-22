# vuelearn

vue init webpack vueLearn

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).




https://cn.vuejs.org/

模板语法
```
数据绑定：
	1. <span>{{ msg }}</span>			此时当 msg 发生改变时，此处也会相应的改变
	2. <span v-once>{{ msg }}</span>	此时当 msg 发生改变时，此处不会会相应的改变

原始HTML：
	<p>Using v-html directive: <span v-html="rawHtml"></span></p>	v-html 指令 会把 HTML 代码转化成真正的 HTML 代码

指令：
	指令 (Directives) 是带有 v- 前缀的特殊特性。指令的职责是，当表达式的值改变时，将其产生的连带影响，响应式地作用于 DOM。
	指令可以接收参数：
		<a v-bind:href="url">...</a>			: 后面的 href 为 v-bind 的参数，告知 v-bind 指令将该元素的 href 特性与表达式 url 的值绑定。
		<a v-on:click="doSomething">...</a>
	修饰符 是以半角句号 . 指明的特殊后缀，用于指出一个指令应该以特殊方式绑定。
		<form v-on:submit.prevent="onSubmit">...</form>
	缩写：
		Vue.js 为 v-bind 和 v-on 这两个最常用的指令，提供了特定简写：
			<a :href="url">...</a>
			<a @click="doSomething">...</a>

```


计算属性和侦听器
```

```

