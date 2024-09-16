<template>

  <input type="checkbox" v-model="todo.done"/>
  <span :class="{done: todo.done}"> {{ todo.text }}</span>
  <button @click="removeTodo(todo)">X</button>
  <slot><p>Hi</p></slot>
</template>

<script setup lang="ts">
const emit = defineEmits(['remove'])
defineProps({ todo: Object })
function removeTodo(todo) {
  emit('remove', todo)
}
</script>


<style scoped>

</style>