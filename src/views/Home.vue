<template>
  <div class="home">
    <div class="container">
      <div class="row mt-3">
        <div class="col-md-3" v-for="(item,index) in items" :key="index">
          <div class="card">
          <img :src="item.img" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">{{item.name}}</h5>
            <p>{{ item.price }}</p>
            <p class="card-text">{{item.productDetails}}</p>
            <a href="#" class="btn btn-primary">Add to Cart</a>
          </div>
        </div>
        </div>
        <!--
        <div class="col-md-3">
          <div class="card">
          <img src="../assets/Red-Egg.jpg" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
          </div>
        </div>
        </div>
        <div class="col-md-3">
          <div class="card">
          <img src="../assets/Red-Egg.jpg" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
          </div>
        </div>
        </div>
        <div class="col-md-3">
          <div class="card">
          <img src="../assets/Red-Egg.jpg" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
          </div>
        </div>
        </div>
-->
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "Home",
  data(){
    return{
      items:[
        {name:'Rice',price:50,img:'https://picsum.photos/id/1005/600/200',productDetails:"Contrary to popular belief, Lorem Ipsum is not simply random text."},
        {name:'Rice',price:50,img:'https://picsum.photos/id/1005/600/200',productDetails:"Contrary to popular belief, Lorem Ipsum is not simply random text."},
        {name:'Rice',price:50,img:'https://picsum.photos/id/1005/600/200',productDetails:"Contrary to popular belief, Lorem Ipsum is not simply random text."},
        {name:'Rice',price:50,img:'https://picsum.photos/id/1005/600/200',productDetails:"Contrary to popular belief, Lorem Ipsum is not simply random text."},
      ],
    }
  },
  methods:{
    
  }
};
</script>
