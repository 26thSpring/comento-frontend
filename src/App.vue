<template>
  <div id="app">
    <Navbar/>
    <div class="content">
      <router-view/>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar";

export default {
  components: {
    Navbar
  },
  data() {
    return {};
  }
};
</script>

<style lang="less">
@import url(//fonts.googleapis.com/earlyaccess/notosanskr.css);
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
}
a {
  text-decoration: none;
  color: inherit;
  &:visited {
    color: inherit;
  }
}
input,
button {
  font-family: "Noto Sans Kr";
}
* {
  box-sizing: border-box;
}

#app {
  font-family: "Noto Sans Kr", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  min-height: 100%;
}
.content {
  position: absolute;
  width: 100%;
  min-height: calc(100%-5rem);
  top: 5rem;
}
</style>
