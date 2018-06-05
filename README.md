# vuex
vuex,vue的状态管理模式，入门，理解vuex
###vuex是一个状态管理模式，集中式存储管理应用中的所有组件的状态
###包含 state，getter，mutation，action，module属性
##使用vuex插件创建一个仓库，store
## 其中state 用于存储数据；getter类似一个计算属性，当state中的数据更改时，会触发getter属性；
##mutation用于更改state，不建议通过 this.$store.state.数据 更改，而是通过mutation更改，便于追踪状态
##action通过触发mutation更改 state，可以用于异步
##module 在暴露给其他组件时，将store分割成多个模块
###### 每个模块都有自己的state getter mutation action属性
##其中 getter action module不常用
######const moduleA = {
######  state: { ... },
######  mutations: { ... },
######  actions: { ... },
 ###### getters: { ... }
######}

######const moduleB = {
######  state: { ... },
######  mutations: { ... },
######  actions: { ... }
######}

######const store = new Vuex.Store({
######  modules: {
######    a: moduleA,
######    b: moduleB
######  }
######})

######store.state.a // -> moduleA 的状态
######store.state.b // -> moduleB 的状态

##定义 属性方法：
###mutation:{mutation`s Fun(state,[参数]){state.数据=new数据}}
###action:{action`s Fun(context){context.commit(mutation`s Fun)}}
####context 是一个与store实例具有相同方法和属性的对象 ，但并不是store本身


##触发 vuex中store仓库属性的办法：
##mutation this.$store.commit('mutation`s Fun',[参数]);
##action this.$store.dispatch('action`s Fun');
