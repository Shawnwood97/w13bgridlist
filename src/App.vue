<template>
  <div id="app">
    <user-tweets />
  </div>
</template>

<script>
import UserTweets from "./components/userTweets.vue";
export default {
  name: "App",
  components: { UserTweets },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

body {
  background: #1c1c28;
  height: 100%;
}
</style>
