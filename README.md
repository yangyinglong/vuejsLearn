# vuelearn

```
vue init webpack vueLearn
在ubuntu环境下，用上面这句初始化的时候，会出错，所以我用了
sudo vue init webpack vueLearn
这样初始化的项目所属 root，用 sublime 编写的时候，一直要用到 root 权限，很不方便
所以初始化项目之后，把文件的所属分配给 普通用户
sudo chown -R 用户名 vueLearn/
sudo chgrp -R 用户名 vueLearn/
```

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
对于任何复杂逻辑，都应当使用计算属性
computed: {
	reversedMessage: function() {
		return this.message.split('').reverse().join('')
	}
}
其中， reversedMessage 就是一个计算属性，可以直接使用 例如 {{ reversedMessage }}，当 message 发生改变时，reversedMessage 也会改变
计算属性和方法的比较：
	我们可以将同一函数定义为一个方法而不是一个计算属性。两种方式的最终结果确实是完全相同的。然而，不同的是计算属性是基于它们的依赖进行缓存的。只在相关依赖发生改变时它们才会重新求值。这就意味着只要 message 还没有发生改变，多次访问 reversedMessage 计算属性会立即返回之前的计算结果，而不必再次执行函数。
	方法的定义：
		methods: {
		  reversedMessage: function () {
		    return this.message.split('').reverse().join('')
		  }
		}
		使用时， {{ reversedMessage() }}
计算属性的 setter
	计算属性默认只有 getter ，不过在需要时你也可以提供一个 setter ：
		computed: {
		  fullName: {
		    // getter
		    get: function () {
		      return this.firstName + ' ' + this.lastName
		    },
		    // setter
		    set: function (newValue) {
		      var names = newValue.split(' ')
		      this.firstName = names[0]
		      this.lastName = names[names.length - 1]
		    }
		  }
		}

侦听器：
	当需要在数据变化时执行异步或开销较大的操作时，需要 watch 来相应数据的变化
```

Class 与 Style 绑定
```
1. 我们可以传给 v-bind:class 一个对象，以动态地切换 class
2. 你可以在对象中传入更多属性来动态切换多个 class，同时，绑定的数据对象不必内联定义在模板里，可以定义在 data 中
3. 我们也可以在这里绑定一个返回对象的计算属性
4. 我们可以把一个数组传给 v-bind:class，以应用一个 class 列表
5. 根据条件切换列表中的 class，可以用三元表达式
6. 也可以用在组件上

```

条件渲染
```
v-if
v-else-if
v-else

v-else，v-else-if 也必须紧跟在带 v-if 或者 v-else-if 的元素之后。
用 key 管理可复用的元素
例如 ./components/ifElse/ifElseVue.vue 中，加入 key 之后，两个元素是完全独立的，如果不加 key ，input 标签是同一个

v-show
一般来说，v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。因此，如果需要非常频繁地切换，则使用 v-show 较好；如果在运行时条件很少改变，则使用 v-if 较好
```

列表渲染
```
v-for="item in items"
v-for="(item, index) in items"
{{ item.message}} - {{ index }}
其中 data: {
    	items: [
      		{ message: 'Foo' },
      		{ message: 'Bar' }
    	]
  	}
也可以通过一个对象的属性来迭代
v-for="value in object"
{{value}}
data: {
    object: {
      firstName: 'John',
      lastName: 'Doe',
      age: 30
    }
}
可以用两个参数来迭代
v-for="(value, key) in object"
也可以用三个参数来迭代
v-for="(value, key, index) in objece"
```