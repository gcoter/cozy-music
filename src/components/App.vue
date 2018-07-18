<template>
  <div class='app-wrapper o-layout--2panes'>
    <aside class='o-sidebar'>
      <nav>
        <ul class='c-nav'>
          <li class='c-nav-item'>
            <router-link class='c-nav-link' to='/home'>
              <icon class='c-nav-icon' v-bind:icon='navIcon' />
              {{ t('Nav.home_nav') }}
            </router-link>
          </li>
        </ul>
      </nav>
    </aside>
    <main class='app-content'>
      <router-view class="view"></router-view>
    </main>
  </div>
</template>

<script>
import Vue from 'vue'
import VueRouter from 'vue-router'
import navIcon from '../assets/icons/icon-bullet-point.svg'

import icon from './Icon'

import Home from './Views/Home.vue'

// This installs <router-view> and <router-link>,
// and injects $router and $route to all router-enabled child components
Vue.use(VueRouter)

const router = new VueRouter({
  mode: 'hash',
  base: '/',
  linkActiveClass: 'is-active',
  routes: [
    { path: '/home', component: Home },
    { path: '/', redirect: '/home'},
    // default, always at the end
    { path: '*', redirect: '/home'}
  ]
});

export default {
  router,
  components: { icon },
  data () {
    return {
      navIcon
    }
  },
}
</script>
