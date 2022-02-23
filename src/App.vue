<template>
  <div id="app">
    <navbar></navbar>
    <div class="container-fluid">
     <Cart></Cart>
     <router-view></router-view>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Cart from './components/Cart.vue'
export default {
  components:{
    Navbar,
    Cart,
    
  },
  
}
</script>

<style>

</style>
