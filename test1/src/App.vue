<template>
  <div id="app">
    <Navbar></Navbar> 
    	<br> <br>
      <nav class="navbar navbar-expand-sm bg-dark navbar-dark">
        <ul class="navbar-nav">
          <li class="nav-link router-link-exact-active router-link-active">
            <router-link to="/" class="nav-link">Home</router-link>
          </li>
          <li class="nav-link router-link-exact-active router-link-active">
             <router-link to="/about" class="nav-link">About</router-link>
          </li>
          <li class="nav-link router-link-exact-active router-link-active">
             <router-link to="/contact" class="nav-link">Contact</router-link>
          </li>
        </ul>
      </nav>
    <br>
    <br>
    
    <div class="container">
      <div class="row">
        <div class="col-8">
          <router-view></router-view>
        </div>
        <div class="col-4">
          <About></About>
        </div>
      </div>
   </div>
  </div>
</template>

<script>
import Navbar from './component/Navbar'
import Home from './component/Home'
import About from './component/About'
import Contact from './component/Contact'

import VueRouter from 'vue-router'

const routes = [
  { path: '/', component: Home },
  { path: '/about', component: About },
  { path: '/contact', component: Contact }
]

const router = new VueRouter({
  routes, // short for `routes: routes`
  mode: 'history',  
})


export default {
  name: 'app',
  components: {
    Navbar,
    About,
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  router,

}
</script>


