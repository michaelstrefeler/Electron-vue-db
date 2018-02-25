<template>
  <div id="app">
    <div id="wrapper">
      <img id="logo" src="~@/assets/logo.png" alt="electron-vue">
      <nav>
        <router-link :to="{ name: 'landing-page' }" class="menu">Home</router-link>
        <router-link :to="{ name: 'more' }" class="menu">More</router-link>
      </nav>
    <router-view></router-view>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Electron-vue-db'
  }
</script>

<style>
  body {
    overflow-x: hidden;
    overflow-y: scroll;
  }
  nav{
    border: 1px solid black;
  }
  .menu{
    color: red;
    text-decoration: none;
  }
</style>
