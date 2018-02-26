<template>
  <div id="app">
    <div id="wrapper">
      <nav>
        <router-link :to="{ name: 'landing-page' }" class="menu">Home</router-link>
        <router-link :to="{ name: 'more' }" class="menu">More</router-link>
      </nav>
      <img id="logo" src="~@/assets/logo.png" alt="electron-vue">
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
  .menu{
    color: blue;
    text-decoration: none;
  }
</style>
