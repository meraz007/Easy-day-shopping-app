<template>
  <section class=" gradient-custom">
  <div class="container py-5 ">
    <div class="row justify-content-center align-items-center ">
      <div class="col-12 col-lg-9 col-xl-7">
        <div class="card shadow-2-strong card-registration" style="border-radius: 15px;">
          <div class="card-body p-4 p-md-5">
            <h3 class="mb-4 pb-2 pb-md-0 mb-md-5">Registration Form</h3>
            <form @submit.prevent="userRegistration">
              <div class="row">
                <div class="col-md-6 mb-4">
                  <div class="form-outline">
					  <label class="form-label" for="firstName">First Name</label>
                    <input type="text" id="firstName" 
					class="form-control form-control-lg" 
					v-model="userInfo.fName"
					/>
                  </div>
                </div>
                <div class="col-md-6 mb-4">
					<label class="form-label" for="lastName">Last Name</label>
                  <div class="form-outline">
                    <input type="text" id="lastName" 
					class="form-control form-control-lg" 
					v-model="userInfo.lName"
					/>
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-6 mb-4 d-flex align-items-center">
                  <div class="form-outline datepicker w-100">
					  <label for="birthdayDate" class="form-label">Birthday</label>
                    <input
                      type="text"
                      class="form-control form-control-lg"
                      id="birthdayDate"
					  v-model="userInfo.bDate"
                    />
                  </div>
                </div>
                <div class="col-md-6 mb-4">
                  <h6 class="mb-2 pb-1">Gender: </h6>
                  <div class="form-check form-check-inline">
					  <label class="form-check-label" for="femaleGender">Female</label>
                    <input
                      class="form-check-input"
                      type="radio"
                      name="inlineRadioOptions"
                      id="femaleGender"
                      value="option1"
                      checked
					  v-model="userInfo.gender"
                    />
                  </div>

                  <div class="form-check form-check-inline">
					  <label class="form-check-label" for="maleGender">Male</label>
                    <input
                      class="form-check-input"
                      type="radio"
                      name="inlineRadioOptions"
                      id="maleGender"
                      value="option2"
					  v-model="userInfo.gender"
                    />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-6 mb-4 pb-2">
                  <div class="form-outline">
					  <label class="form-label" for="emailAddress">Email</label>
                    <input type="email" id="emailAddress" 
					class="form-control form-control-lg" 
					v-model="userInfo.email"
					/>
                  </div>
                </div>
                <div class="col-md-6 mb-4 pb-2">
					<label class="form-label" for="phoneNumber">Phone Number</label>
					<div class="form-outline">
						<input type="tel" id="phoneNumber" 
						class="form-control form-control-lg" 
						v-model="userInfo.pNumber"
						/>
					</div>
                </div>
              </div>
              <div class="mt-4 pt-2">
                <input class="btn btn-primary btn-lg" type="submit" value="Submit" />
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
</template>

<script>
export default {
	data(){
		return{
			userInfo:{
				fName:"",
				lName:"",
				bDate:null,
				gender:"",
				email:"",
				pNumber:""
			}
		}
	},
	methods:{
		userRegistration(){

		}
	}
}
</script>

<style scoped>
*{
    margin: 0px;
    padding: 0px;
}
.gradient-custom {
  background: #6a11cb;
  background: -webkit-linear-gradient(to right, rgba(106, 17, 203, 1), rgba(37, 117, 252, 1));
  background: linear-gradient(to right, rgba(106, 17, 203, 1), rgba(37, 117, 252, 1))
}

.card-registration .select-input.form-control[readonly]:not([disabled]) {
  font-size: 1rem;
  line-height: 2.15;
  padding-left: .75em;
  padding-right: .75em;
}
.card-registration .select-arrow {
  top: 13px;
}
</style>