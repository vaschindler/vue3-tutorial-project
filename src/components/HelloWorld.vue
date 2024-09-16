<template>
  <p ref="pElementRef">{{ msg }}</p>

  <div class="container">
    <button @click="enableClassAPI = !enableClassAPI">Enable CounterClassAPI</button>
    <CounterClassAPI v-if="enableClassAPI"/>
    <button @click="enableOptionsAPI = !enableOptionsAPI">Enable CounterOptionsAPI</button>
    <CounterOptionsAPI v-if="enableOptionsAPI"/>
    <button @click="enableCompositionAPI = !enableCompositionAPI">Enable CounterCompositionAPI</button>
    <CounterCompositionAPI v-if="enableCompositionAPI"/>
    <div class="todolist">
      <ToDoListCompositionAPI/>
    </div>
  </div>


</template>

<script setup lang="ts">
import CounterClassAPI from "@/components/CounterClassAPI.vue";
import {ref} from "vue";
import CounterCompositionAPI from "@/components/CounterCompositionAPI.vue";
import CounterOptionsAPI from "@/components/CounterOptionsAPI.vue";
import ToDoListCompositionAPI from "@/components/ToDoListCompositionAPI.vue";

defineProps({
  msg: String
})
const pElementRef = ref(null)
const enableClassAPI = ref(false)
const enableOptionsAPI = ref(false)
const enableCompositionAPI = ref(false)

// onMounted(() => {
//   pElementRef.value.textContent = 'mounted!'
// })
</script>

<style scoped>
.container {

  display: flex;
  flex-direction: row;
  align-items: center;
}

.todolist {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-left: 100px;
}

</style>
