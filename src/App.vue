<template>
  <UserProfile />
</template>

<script>
import UserProfile from "./components/UserProfile";
export default {
  name: "App",
  components: {
    UserProfile,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-size: 62.5%;
  background: #f3f3f3;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: grid;
  grid-template-columns: 10rem 1fr 10rem;
  justify-items: start;
  margin-top: 2rem;
}

#app > * {
  grid-column: 2 / -2;
}
</style>
