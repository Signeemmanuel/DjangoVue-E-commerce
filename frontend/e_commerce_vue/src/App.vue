<template>
  <div id="wrapper">
    <nav class="w-full flex justify-between items-center p-4 bg-black text-white">
      <div class="navbar-brand">
        <router-link to="/" class="navbar-item"
          ><strong>E-Commerce</strong></router-link
        >
        <a aria-label="menu" aria-expanded="false" data-target="navbar-menu">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
      <div id="navbar-menu">
        <div class="flex gap-4 justify-evenly items-center">
          <router-link to="/summer" class="navbar-item">Summer</router-link>
          <router-link to="/winter" class="navbar-item">Winter</router-link>
          <div class="navbar-item">
            <div class="flex gap-4">
              <router-link to="/log-in" class="bg-white text-black p-2 rounded"
                >Log in</router-link
              >
              <router-link to="/cart" class="bg-green-600 p-2 rounded">
                <font-awesome-icon icon="shopping-cart" />
                <span> Cart</span>
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </nav>
    <section>
      <router-view />
    </section>
    <footer>
      <p class="text-center">Copyright (c) 2023</p>
    </footer>
  </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { faShoppingCart } from '@fortawesome/free-solid-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

library.add(faShoppingCart)
export default {
  components: {
    FontAwesomeIcon
  }
}
</script>
<style></style>
