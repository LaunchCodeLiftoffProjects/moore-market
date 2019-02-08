<template>
    <div class="log">
        <h1>Moore Market Login</h1>
        <form @submit.prevent="onSubmit">
            <div>
                <ul>
                    <li><input type="text" placeholder="username" v-model="username" v-validate="'required'" name="username" /></li>
                </ul>
                <div>
                    <span>{{ errors.first('username') }}</span>
                </div>
            </div>
            <div>
                <ul>
                    <li><input type="email" placeholder="email" v-model="email" v-validate="'required'" name="email" /></li>
                </ul>
                <div>
                    <span>{{ errors.first('email') }}</span>
                </div>
            </div>

            <button type="submit" class="ui submit button">Submit</button><br />
            <p> Dont have an account? <a href="SignUp.vue">Sign Up Now! </a> </p>
        </form>
    </div>
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
                email: ""
                
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
<style scoped>
    div.error {
        color: #9f3a38;
    }
    .log {
        display: block;
        border: 7px solid red;
        padding: 10px;
        width: 300px;
        margin: 250px;
    }

    
    h1 {
        text-align: center;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }
</style>