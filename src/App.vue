<template>
  <router-view />
</template>

<style lang="scss">
@import url("https://use.fontawesome.com/releases/v5.15.2/css/all.css");
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap");

$rosaFixe: #ffeff1;

#app {
  font-family: "Poppins", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  margin: 0;
  padding: 0;
}

html {
  font-family: "Poppins", sans-serif;
}

body {
  background-color: $rosaFixe;
  color: #2c3e50;
  transition: all 0.5s cubic-bezier(0.075, 0.82, 0.165, 1);
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: steelblue;
    }
  }
}
</style>
