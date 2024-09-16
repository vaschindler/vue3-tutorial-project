<!-- OptionsComponent.vue -->
<template>
  <div>
    <h1>Options API with Computed Property</h1>

    <input v-model="newItem" placeholder="Add new item"/>

    <button @click="addItem">Add Item</button>

    <button @click="toggleVisibility">
      {{ isVisible ? 'Hide' : 'Show' }} List
    </button>

    <p>Total items: {{ itemCount }}</p>

    <ul v-if="isVisible">
      <li v-for="(todo, index) in items" :key="index">{{ todo }}</li>
      <button @click="removeTodo(todo)">X</button>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: ['Item 1', 'Item 2', 'Item 3'],
      newItem: '',
      isVisible: true,
    };
  },
  computed: {
    itemCount() {
      return this.items.length;
    },
  },
  watch: {
    items(newItems) {
      console.log('Items changed' + newItems);
    },
    deep: true,
  },
  props: {
    hideCompleted: Boolean,
  },
  emits: ['remove'],
  methods: {
    addItem() {
      if (this.newItem.trim()) {
        this.items.push(this.newItem);
        this.newItem = '';
      }
    },
    toggleVisibility() {
      this.isVisible = !this.isVisible;
    },
    removeTodo(todo) {
      this.items = this.items.filter((item) => item !== todo);
    },
  },
};
</script>

<style scoped>
button {
  margin: 5px;
}
</style>