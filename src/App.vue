
<template>
  <RouterView />
</template>

<script setup>
</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@500&family=Reddit+Mono:wght@500&display=swap');

#app , html, body {
  font-family: "Reddit Mono", monospace;
  font-optical-sizing: auto;
  font-weight: 500;
  font-style: normal;

  margin: 0;
  padding: 0;
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
