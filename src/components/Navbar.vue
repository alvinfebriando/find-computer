<template>
  <div class="navbar">
    <div>FindComputer</div>
    <div class="nav-links">
      <router-link v-if="isLoggedIn" to="/">Home</router-link>
      <router-link v-if="isLoggedIn" to="/search">Search</router-link>
      <router-link v-if="isLoggedIn" to="/account">Account</router-link>
      <router-link v-if="!isLoggedIn" to="/login">Log In</router-link>
      <router-link v-else to="/logout">Log Out</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  computed: {
    isLoggedIn() {
      return this.$store.state.isLoggedIn;
    },
  },
};
</script>

<style>
.navbar {
  display: flex;
  justify-content: space-around;
}

.nav-links {
  width: 30%;
  display: flex;
  justify-content: space-around;
}

.search {
  width: 20%;
}
</style>
