<template>
  <div class="navbar">
    <div class="logo-wrapper">
      <a href="/">v-notes</a>
    </div>
    <div class="menu">
      <router-link to="/about">About</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style lang="scss">
@import "../styles/variables";
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: $navbar;
  height: 50px;
  padding-right: 20px;
  .logo-wrapper {
    width: 200px;
    height: 50px;
    background: $primary;
    text-align: center;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    a {
      vertical-align: middle;
      padding: 0;
      margin: 0;
      color: white;
      font-weight: bold;
      text-decoration: none;
    }
  }
  .menu {
    a {
      font-weight: bold;
      color: #777;
      text-decoration: none;

      &.router-link-exact-active {
        color: $primary;
      }
    }
  }
}
</style>
