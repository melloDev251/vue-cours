<template>
<Header/>
  <h1>User connected ! Welcome to Home Page</h1>
</template>

<script>
import Header from './Header.vue'
export default {
    name:'Home',
    components:{
        Header
    },
    mounted(){
        let user = localStorage.getItem('user-info')
        if(!user){
            this.$router.push({name:'SignUp'})

        }
    }
}
</script>

<style>

</style>