<template>

<div class="container">
    <div class="row justify-content-center">
    <div class="col-md-8">
        <div v-show="alertShow" class="alert alert-info" role="alert">
            Thanks For Your Order....
          </div>
          <p v-if="errors.length" class="alert alert-danger" role="alert">
            <ul>
            <li v-for="(error,index) in errors" :key="index">{{ error }}</li>
            </ul>
        </p>
        <h1>Billing Details</h1>
        <hr>
      <form @submit.prevent="checkForm">
        <div class="row">
          <div class="col-md-6 mb-3">
            <label for="firstName">First name</label>
            <input type="text" class="form-control" v-model="userInput.fName">
          </div>
          <div class="col-md-6 mb-3">
            <label for="lastName">Last name</label>
            <input type="text" class="form-control" id="lastName" v-model="userInput.lName">
          </div>
        </div>

        <div class="mb-3">
          <label for="username">Username</label>
          <div class="input-group">
            <input type="text" class="form-control" 
            placeholder="Username" 
            v-model="userInput.userName">
          </div>
        </div>

        <div class="mb-3">
          <label for="email">Email</label>
          <input type="email" class="form-control" id="email" 
          placeholder="you@example.com"
          v-model="userInput.email">
        </div>

        <div class="mb-3">
          <label for="address">Address</label>
          <input type="text"
           class="form-control" 
           id="address"
           v-model="userInput.address">
        </div>
        <hr class="mb-4">
        <h4 class="mb-3">Payment</h4>

        <div class="d-block my-3">
          <div class="custom-control custom-radio">
            <input id="credit" name="paymentMethod" type="radio" class="custom-control-input" >
            <label class="custom-control-label" for="credit">Credit card</label>
          </div>
          <div class="custom-control custom-radio">
            <input id="debit" name="paymentMethod" type="radio" class="custom-control-input" >
            <label class="custom-control-label" for="debit">Debit card</label>
          </div>
          <div class="custom-control custom-radio">
            <input id="paypal" name="paymentMethod" type="radio" class="custom-control-input" >
            <label class="custom-control-label" for="paypal">PayPal</label>
          </div>
        </div>
        <div class="row">
          <div class="col-md-6 mb-3">
            <label for="cc-name">Name on card</label>
            <input type="text" class="form-control" id="cc-name" placeholder="" >
            <small class="text-muted">Full name as displayed on card</small>
          </div>
          <div class="col-md-6 mb-3">
            <label for="cc-number">Credit card number</label>
            <input type="text" class="form-control" id="cc-number" placeholder="" >
          </div>
        </div>
        <div class="row">
          <div class="col-md-3 mb-3">
            <label for="cc-expiration">Expiration</label>
            <input type="text" class="form-control" id="cc-expiration" placeholder="" >
          </div>
          <div class="col-md-3 mb-3">
            <label for="cc-cvv">CVV</label>
            <input type="text" class="form-control" id="cc-cvv" placeholder="" >
          </div>
        </div>
        <hr class="mb-4">
        <button class="btn btn-success btn-lg btn-block" type="submit">Submit</button>
      </form>
    </div>
  </div>
</div>
</template>

<script>

export default {
components:{
},
data(){
    return{
        alertShow:false,
        userInput:{
            fName:"",
            lName:"",
            userName:"",
            email:"",
            address:""
        },
        errors :[]
    }
},
methods:{
    checkForm(){
        if(!this.userInput.fName){
            this.errors.push('First Name required')
        }
        if(!this.userInput.lName){
            this.errors.push('Last Name required')
        }
        if(!this.userInput.userName){
            this.errors.push('UserName required')
        }
        if(!this.userInput.email){
            this.errors.push('Email required')
        }
        if(!this.userInput.address){
            this.errors.push('Address required')
        }
        if(!this.errors.length){
            this.alertShow=true
            setTimeout(()=>this.$router.push('/'),2000)
        }
    }
}

}
</script>

<style>

</style>