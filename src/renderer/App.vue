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
    overflow-y: auto;
  }

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  #wrapper {
    background:
      radial-gradient(
        ellipse at top left,
        rgba(255, 255, 255, 1) 40%,
        rgba(229, 229, 229, .9) 100%
      );
    height: 100vh;
    padding: 20px 80px 60px;
    width: 100vw;
  }

  #logo {
    height: auto;
    margin-bottom: 20px;
    width: 420px;
  }

  main {
    display: flex;
    justify-content: space-between;
  }

  main > div { flex-basis: 50%; }

  .left-side {
    display: flex;
    flex-direction: column;
  }

  .welcome {
    color: #555;
    font-size: 23px;
    margin-bottom: 10px;
  }

  .title {
    color: #2c3e50;
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 6px;
  }

  .title.alt {
    font-size: 18px;
    margin-bottom: 10px;
  }

  .doc p {
    color: black;
    margin-bottom: 10px;
  }

  .dataTitle{
    text-decoration: underline;
  }
</style>
