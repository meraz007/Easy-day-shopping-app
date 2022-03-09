<template>
  <div class="container">
      <div class="row justify-content-center mt-4">
          <div class="col-md-8">
              <img :src="item.photo" alt="">
              <div class="float-end">
                <h1>{{ item.title }}</h1>
                <p>{{ item.description }}</p>
                <p><span class="fw-bold">Price $</span> {{item.price}}</p>
                <button @click="addItem(item)" class="btn btn-success">Add To Cart</button>
              </div>
              
          </div>
      </div>
  </div>
</template>

<script>
//import axios from 'axios'
import SourceData from '../Data/data.json'
export default {   
    data(){
        return{
            data:SourceData.products
        }
    },
    computed:{
        itemId(){
           return parseInt(this.$route.params.id)
        },
        item(){
            return SourceData.products.find(item =>item.id===this.itemId)
        }
    },
    methods:{
        
        addItem(item){
            this.$store.commit('addToCart',item)
        },
    }
}
</script>

<style>

</style>