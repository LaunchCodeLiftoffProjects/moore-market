<template>
    <form @submit.prevent="onSubmit">
        
            <div class="Signup">

                <h1>Moore Market Signup</h1>
                <ul>
                    <li><input type="text" placeholder="Username" v-model="username" v-validate="'required|min:4|max:15'" name="username" /></li>
                </ul>
                <div>
                    <span>{{ errors.first('username') }}</span>
                </div>
            
            <ul>
                <li><input type="email" placeholder="Email" v-model="email" v-validate="required" name="email" /></li>
            </ul>
            <div>
                <span>{{ errors.first('email') }}</span>
            </div>

            <ul>
                <li><input type="password" placeholder="Password" v-model="password" v-validate="'required|min:4|max:10|confirmed'" name="passwword" /></li>
            </ul>
            <div>
                <span>{{ errors.first('password') }}</span>
            </div>

            <ul>
                <li><input type="password" placeholder="Confirm Password" v-model="confirmpassword" v-validate="'required|confirmed:password'" name="comfirmpassword" /></li>
            </ul>
            <div>
                <span>{{ errors.first('confirmpassword') }}</span>
            </div>

            <div class=" checkbox">
                <label>Type Of Account</label><br />

                <input type="checkbox" id="customer" value="customer" name="customer"><label for="customer">Customer</label><br>
                <input type="checkbox" id="vendor" value="vendor" name="vendor"><label for="vendor">Vendor</label><br>
                <input type="checkbox" id="foodbank" value="foodbank" name="foodbank"><label for="foodbank">Food Bank</label><br />
            </div>
            <button>Sign Up Now</button><br />

            <p> Already have a account? <a href="Login.vue">Login Now! </a> </p>
            </div>
            





        </form>
</template>

<script>
    import Vue from "vue";
    import VeeValidate from "vee-validate";
    Vue.use(VeeValidate);
    export default {
        name: "Login",
        data() {
            return {
                username: "",
                email: "",
                password: "",
                confirmpassword:""

            };
        },
        methods: {
            onSubmit() {
                this.$validator.validateAll().then(result => {
                    if (result) {
                        alert("submit");
                    }
                });
            }
        }
    };
</script>
  
<style>
    .Signup {
        display:block;
        border: 7px solid red;
        padding: 10px;
        width: 300px;
        margin: 250px;
    }
    .checkbox{
        border: solid black;
        border-width: 3px;

        

    }

    h1 {
        text-align: center;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: block;
        vertical-align: middle;
        margin: 0 10px;
    }

    
</style>
