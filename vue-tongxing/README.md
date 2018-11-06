# vue-tongxing

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

#vue 组件通信

- 1. props/自定义事件

- 2. 事件总线（event bus）
	
- 3. Vuex状态管理

- 4. 其他的通信方式
	深层次组件$attrs 和 $listeners
	provide 和 inject 组件库使用的比较多

#props/自定义事件
可以给组件定制数据，也就是传入参数，利用props来实现
组件内部交互后，会通知外界组件内部的状态，利用自定事件完成

- 单向数据流
	父级 prop 的更新会向下流动到子组件中，
	但是反过来则不行。
	这样会防止从子组件意外改变父级组件的状态
	从而导致你的应用的数据流向难以理解。

- 组件的双向数据绑定
	在默写情况下，父组件直接改变props会使
	数据改变更加方便些。
	使用修饰符 .sync
	使用指令v-model

- 跨多层组件通信
    兄弟组件间的通信，可以采用 状态提升 的方式，讲状态提升到两个组件最近的公共父级上。

- 事件总线（event bus）
    new Vue的实例上会有两个方法，$on $emit
    利用$on 来监听事件，$emit发布事件
    利用这样的方式，只要能访问到公用的实例，都可以随意的监听发布任意事件。

    1. 作为插件，创建新的实例
    2. 使用$root访问根实例


#
register-service-worker 
当开启之后，在打包后，生成一个service-worker.js文件，

当访问应用的时候，会做一个缓存，缓存在service worker，当网络断了，依然可以访问页面

缓存页面

是一个模块 
	npm i http-server -g

	 快速启动一个服务


父子组件
	哪一个组件使用在另一个组件的模板中，称之为哪一个组件是子组件，另一个是父组件

	父-> 子  props
	子 -> 父
		子组件内发布一个自定的事件，父组件监听这个自定的事件
			发布 $emit
			监听 v-on

	单向数据流 父组件向子组件传递数据，子组件不允许修改这个数据

	父组件的 title 使用在很多地方 

		有一个组件改变了title，其他组件也要改正

	和组件双向数据绑定
		父组件传参给子组件 子组件中可以改变这个数据

	组件上也可以写v-model
		v-model 语法糖
			传入value值
			监听input事件	----  chang事件


组件可以复用 通用    







