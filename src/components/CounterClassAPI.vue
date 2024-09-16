<template>
  <div class="container">
  <button @click="incrementCounter">Add one</button>
  <p>Counter: {{ counter }}</p>
  <p>{{ message  }}</p>

  <button @click="counter = 0">Reset</button>
  </div>
</template>
<script lang="ts">
import { Vue, Component, toNative } from 'vue-facing-decorator'

@Component({
  name: 'CounterClassAPI'
})
class CounterClassAPI extends Vue {
  counter = 0
  message = 'Hello World'

  incrementCounter() {
    this.counter++
  }
}
export default toNative(CounterClassAPI);
</script>



<style scoped>
.container {
  margin: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>