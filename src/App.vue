<script setup lang="ts">
import JobTitleGenerator from "./components/JobTitleGenerator.vue";
</script>

<template lang="pug">
.flex.flex-col.lg_grid.grid-cols-1.lg_grid-cols-2.lg_gap-2.gap-8.h-full
  .relative.bg-special-green
    .absolute.w-full.py-8.text-5xl.font-bold.shit Super Tech Job Title Generator
    img(alt="Professionals" src="./assets/professionals.jpg")
  JobTitleGenerator
</template>

<style>
html,
body,
#app {
  height: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  background: #2c72e9;
}

.shit {
  font-family: "Comic Neue", cursive;
  color: lightyellow;
  text-shadow: 2px 2px #7c1414;
}

.bg-special-green {
  background: #acd7c6;
  max-height: 50vh;
  display: flex;
  justify-content: center;
}

.bg-special-green img {
  max-height: 50vh;
}

@media (min-width: 1024px) {
  .bg-special-green {
    max-height: 100%;
    height: 100%;
    display: block;
  }

  .bg-special-green img {
    max-height: 100%;
    width: 100%;
  }
}
</style>
