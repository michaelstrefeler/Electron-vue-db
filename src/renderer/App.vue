<template>
  <div id="app">
      <Menu mode="horizontal" theme="light" active-name="1">
        <router-link :to="{ name: 'landing-page' }" class="menu">
          <MenuItem name="1">
              <Icon type="home"></Icon>
              Home
          </MenuItem>
        </router-link>
        <router-link :to="{ name: 'more' }" class="menu">
          <MenuItem name="2">
              <Icon type="information-circled"></Icon>
              About
          </MenuItem>
        </router-link>
    </Menu>
    <div id="wrapper">
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
    font-weight: 500;
    color:black;
    font-size: 100%;
    overflow-x: hidden;
    overflow-y: scroll;
  }
  .menu{
    color: blue;
    text-decoration: none;
  }
</style>
