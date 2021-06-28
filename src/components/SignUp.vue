<template>
    <img class="logo" src="../assets/image.jpg" alt="logo">
    <h1>Sign Up </h1>
        <div  class="register">
            <input v-model="name" type="text" placeholder="enter name">
            <input v-model="email" type="email" placeholder="enter email">
            <input v-model="password" type="password" placeholder="enter password">
            <button v-on:click="signUp">Register</button>
            <p>
                <router-link to="/login">Sign In</router-link>
            </p>
        </div>
   
</template>

<script>
import axios from 'axios'
export default {
    name:'SignUp',
    methods:{
        async signUp(){
            let result = await axios.post('http://localhost:3000/user', {
                name:this.name,
                email:this.email,
                password:this.password
            })
            console.log(result);
            if(result.status == 201){
                alert("add succesfully")
                localStorage.setItem("user-info", JSON.stringify(result.data))
                this.$router.push({name:'Home'})
            }
        }
    },
    data(){
        return {
            name:'',
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