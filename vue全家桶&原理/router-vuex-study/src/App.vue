<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <!-- 占位符 -->
    <p @click="$store.commit('add')">{{ $store.state.count }}</p>
    <p @click="click">async{{ $store.state.count }}</p>
    <router-view />
  </div>
</template>
<script>
export default {
  methods: {
    click() {
      console.log(this.$store);
      this.$store.dispatch("add");
    },
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
