<template>
  <div class="container">
  <button @click="incrementCounter">Add one</button>
  <p>Counter: {{ counter }}</p>

  <button @click="counter = 0">Reset</button>
    <-- two way binding -->
    <input v-model="text" placeholder="Type here">
    <p>{{ text }}</p>

  </div>
</template>
<script setup lang="ts">
import {ref} from 'vue'

const counter = ref(0)
const text = ref('')

const incrementCounter = () => {
  // change component state by mutating refs
  counter.value++
}

</script>


<style scoped>
.container {
  margin: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>