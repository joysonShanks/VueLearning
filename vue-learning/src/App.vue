<template>
  <div id="app">
    <!-- <ul>
      <li><router-link to="/">/</router-link></li>
      <li><router-link to="/post/1">/post/1</router-link></li>
      <li><router-link to="/post/2">/post/2</router-link></li>
      <li><router-link to="/post/3">/post/3</router-link></li>
    </ul> -->
    <TodoHeader author='Joyson'></TodoHeader>
    <router-view class="view"></router-view>
    <TodoFooter author='Joyson'></TodoFooter>
  </div>
</template>

<script>
import Vue from 'vue'
import VueRouter from 'vue-router'
import Vuetify from 'vuetify'

import Post from './components/Post.vue'
import TodoHeader from './components/Header.vue'
import TodoFooter from './components/Footer.vue'
import Todo from './components/Todo.vue'

Vue.use(VueRouter)
Vue.use(Vuetify)

const router = new VueRouter({
  mode: 'history',
  base: __dirname,
  routes: [
    { path: '/', component: Todo },
    { path: '/post/:id', component: Post }
  ]
})

export default {
  name: 'app',
  router,
  components: {
    TodoHeader,
    TodoFooter
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
