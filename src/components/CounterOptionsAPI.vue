<template>
  <div class="container">
  <button @click="incrementCounter">Add one</button>
  <p>Counter: {{ counter }}</p>

  <button @click="counter = 0">Reset</button>

  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CounterOptionsAPI',
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    incrementCounter() {
      this.counter++
    }
  }
})




</script>



<style scoped>
.container {
  margin: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>