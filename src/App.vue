<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  /* background: hsl(240, 30%, 10%); */
  /* background: linear-gradient(to bottom right, #c8d8e8, #b6d6a2 50%); */
  height: 100vh;
  scroll-behavior: smooth;
}

* {
  margin: 0;
  left: 0;
  box-sizing: border-box;
}
body {
  background: hsl(240, 30%, 10%);
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: whitesmoke;
  /* color: #2c3e50; */
  text-decoration: none;
  transition: 0.5s;
}

#nav a:hover {
  color: aqua;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
