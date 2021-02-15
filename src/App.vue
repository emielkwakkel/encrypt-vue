<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/encrypt">Encrypt</router-link>
  </div>
  <router-view/>
</template>

<style>
body {
    background: #42b983;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  padding: 30px;
  text-align: center;
}
h1 {
  text-align: center;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #fff;
}

h3 {
  margin: 20px 0 0;
}
</style>
