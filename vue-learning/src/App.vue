<template>
  <div id="app">
    <!-- <ul>
      <li><router-link to="/">/</router-link></li>
      <li><router-link to="/post/1">/post/1</router-link></li>
      <li><router-link to="/post/2">/post/2</router-link></li>
      <li><router-link to="/post/3">/post/3</router-link></li>
    </ul> -->
    <Header author='Joyson'></Header>
    <router-view class="view"></router-view>
    <Footer author='Joyson'></Footer>
  </div>
</template>

<script>
import Vue from 'vue'
import VueRouter from 'vue-router'
import Post from './components/Post.vue'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Todo from './components/Todo.vue'

Vue.use(VueRouter)

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
    Header,
    Footer
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
