<!-- CompositionComponent.vue -->
<template>
  <div>
    <h1>Composition API </h1>

    <input v-model="newItem" placeholder="Add new item"/>

    <button @click="addItem">Add Item</button>

    <button @click="toggleVisibility">
      {{ isVisible ? 'Hide' : 'Show' }} List
    </button>

    <p>Total items: {{ itemCount }}</p>
    <p>{{ logMessage }}</p>


    <ul v-if="isVisible">
      <li v-for="todo in filteredItems" :key="todo.id">
        <input type="checkbox" v-model="todo.done"/>
        <span :class="{done: todo.done}"> {{ todo.text }}</span>
        <button @click="removeTodo(todo)">X</button>
<!--        <ChildComponent :todo="todo" @remove="removeTodo"> <p>HALLO</p> </ChildComponent>-->
      </li>
    </ul>
    <button @click="hideCompleted = !hideCompleted">Abgeschlossene ausblenden</button>
  </div>
</template>

<script setup>
import {computed, ref, watch} from 'vue';
import ChildComponent from "@/components/ChildComponent.vue";

let id = 0;
// Reactive variables
const hideCompleted = ref(false);
const items = ref([
  {id: id++, text: 'Aufräumen', done: false},
  {id: id++, text: 'Essen machen', done: true},
  {id: id++, text: 'Javascript lernen', done: true}
]);
const newItem = ref('');
const isVisible = ref(true);
const logMessage = ref('');

const emits = defineEmits(['hello']);


/* A computed property tracks other reactive state used in its computation as dependencies.
 It caches the result and automatically updates it when its dependencies change.*/
const itemCount = computed(() => items.value.length);

const addItem = () => {
  if (newItem.value.trim()) {
    items.value.push({id: id++, text: newItem.value, done: false});
    newItem.value = ''; // Clear input after adding
  }

};

const removeTodo = (todo) => {
  items.value = items.value.filter((item) => item !== todo);
};

const toggleVisibility = () => {
  isVisible.value = !isVisible.value;
};

const filteredItems = computed(() => {
  return hideCompleted.value ? items.value.filter((item) => !item.done) : items.value;
});

//watch() can directly watch a ref, and the callback gets fired whenever the value changes
// Watcher to react to changes in the items array
watch(items, (newItems) => {
  logMessage.value = `List updated! Total items: ${newItems.length}`;
}, { deep: true });

</script>

<style scoped>
button {
  margin: 5px;
}

.done {
  text-decoration: line-through;
}
</style>