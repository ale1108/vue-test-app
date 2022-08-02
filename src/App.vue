<script>
import AgeCalculator from "@/components/AgeCalculator";
import AppHeader from "@/components/AppHeader";

export default {
  name: "App",
  components: {
    AgeCalculator,
    AppHeader,
  },
};
</script>

<template>
  <div id="app">
    <AppHeader></AppHeader>
    <AgeCalculator></AgeCalculator>
  </div>
</template>

<style>
body {
  background-image: url(https://lh4.googleusercontent.com/7Nj0WNSqcXc7QcLL9Cr_AfJv0M2SGI2oq14pitTCKOrouFzhXcn_yBNnqfHFvOK8kJ8=w2400);
  background-repeat: no-repeat;
  background-position: left top;
  background-attachment: fixed;
  background-size: 500px 400px;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
}

html,
* {
  font-family: "Open Sans", sans-serif;
  margin: 0 0;
}
</style>
