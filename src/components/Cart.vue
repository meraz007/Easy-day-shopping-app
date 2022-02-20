<template>
  <div>
    <button class="btn btn-success float-end" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasRight" aria-controls="offcanvasRight"><i class="bi bi-bag"></i>Cart({{itemLength}})</button>
    <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasRight" aria-labelledby="offcanvasRightLabel">
      <div class="offcanvas-header">
        <button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
      </div>
      <div class="offcanvas-body">
        <div v-if="itemLength > 0">
          <div v-for="(item,index) in items" :key="index">
            <p>{{item.title}}-- {{item.price}} <button @click="removeItem(index)" class="btn btn-danger">X</button></p>
            <hr>
          </div>
        </div>
        <div v-else>
          <h1>Please Added A Item!</h1>
        </div>
        <div v-if="itemLength> 0">
        <p>Total Price: {{ totalPrice }} </p>
        <router-link :to="{ path: '/checkout' }">
          <button class="btn btn-success"  
          data-bs-dismiss="offcanvas" 
          aria-label="Close">
          CheckOut
          </button>
        </router-link>
        </div>
      </div>
    </div>
      </div>
</template>

<script>

export default {
  methods:{
    removeItem(index){
      this.items.splice(index,1)
    }
  },
  computed:{
    items(){
      return this.$store.getters.getCart
    },
    itemLength(){
      return this.items.length
    },
    totalPrice(){
    var total=0;
    this.items.forEach(item => {
      total +=parseFloat(item.price)
      total.toFixed(2)
    });
    return total
  }
  }

}
</script>

<style>

</style>