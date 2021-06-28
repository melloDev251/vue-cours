<template>
  <router-view />
</template>


<script>
export default {
  name: 'App',

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
body{
  padding: 0;
  margin: 0;
}
.logo{
    width: 100px;
}

.register input, .login input{
    width: 300px;
    height: 40px;
    padding: 20px;
    display: block;
    margin-bottom: 30px;
    margin-left: auto;
    margin-right: auto;
    border: 1px solid skyblue;
}
.register button, .login button{
    width: 320px;
    height: 40px;
    border: 1px solid skyblue;
    background: skyblue;
    color: #fff;
    cursor: pointer;
}
.nav{
  background-color: #333;
  overflow: hidden;
}
.nav a{
  float: left;
  color: #f2f2f2f2;
  padding: 14px 16px;
  text-align: center;
  text-decoration: none;
  margin-right: 5px;
  font-size: 17px;
}
.nav a:hover{
  background: #ddd;
  color: #333;
}
</style>
