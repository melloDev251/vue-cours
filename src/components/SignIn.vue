<template>
  <h1>Sign In</h1>
  <div  class="login">
        <input v-model="email" type="email" placeholder="enter email">
        <input v-model="password" type="password" placeholder="enter password">
        <button v-on:click="login" >Login</button>
        <p>
            <router-link to="/register">Sign Up Free</router-link>
        </p>
  </div>
   
</template>

<script>
import axios from 'axios'
export default {
    name: 'SignIn',
    methods: {
        async login(){
            let result = await axios.get(`http://localhost:3000/user?email=${this.email}&password=${this.password}`)
            console.log(result);
            if(result.status == 200 && result.data.length>0){
                alert("logged succesfully")
                localStorage.setItem("user-info", JSON.stringify(result.data[0]))
                this.$router.push({name:'Home'})
            }
        }
    },
    data(){
        return {
            email:'',
            password:''
        }
    },
     mounted(){
        let user = localStorage.getItem('user-info')
        if(user){
            this.$router.push({name:'Home'})

        }
    }
}
</script>

<style>

</style>