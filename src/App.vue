<template>
  <div id="app">
    <img class="logo" src="./assets/images/logo.png">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  /*font-family: Microsoft Yahei,Tahoma,Helvetica,Arial,"\5b8b\4f53",sans-serif;*/
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
  .logo{
    width:130px;
    margin:7px 0 0px;
  }
</style>
