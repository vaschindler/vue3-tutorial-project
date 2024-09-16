<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="wrapper">
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" />
  </div>
    <HelloWorld msg="You did it!"  class="helloworld"/>
<!--    <nav>-->
<!--      <RouterLink to="/">Home</RouterLink>-->
<!--      <RouterLink to="/about">About</RouterLink>-->
<!--    </nav>-->

<!--  <RouterView />-->
</template>

<style scoped>

.logo {
  margin-top: 3rem;
  width: 125px;
  height: 125px;
}
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.helloworld {
  display: flex;
  flex-direction: row;
  align-items: center;
  flex-wrap: wrap;
}
</style>
