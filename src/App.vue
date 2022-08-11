<template>
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
  padding: 0;
  box-sizing: border-box;
}
body {
  /* background: hsl(240, 30%, 10%); */
  background: linear-gradient(
    hsl(240, 30%, 10%),
    hsla(180, 2%, 88%, 0.664) 350%
  );
}
</style>
