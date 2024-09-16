<!-- ClassComponent.vue -->
<template>
  <div>
    <h1>Class API with Computed Property</h1>

    <input v-model="newItem" placeholder="Add new item"/>

    <button @click="addItem">Add Item</button>

    <button @click="toggleVisibility">
      {{ isVisible ? 'Hide' : 'Show' }} List
    </button>

    <p>Total items: {{ itemCount }}</p>

    <ul v-if="isVisible">
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script lang="ts">
import {Component, Prop, Vue} from "vue-facing-decorator";

@Component({
  name: 'ClassComponent',
  emits: ['remove']

})
export default class ClassComponent extends Vue {

  items = ['Item 1', 'Item 2', 'Item 3'];
  newItem = '';
  isVisible = true;

  @Prop hideCompleted: boolean;


  get itemCount() {
    return this.items.length;
  }

  addItem() {
    if (this.newItem.trim()) {
      this.items.push(this.newItem);
      this.newItem = '';
    }
  }

  toggleVisibility() {
    this.isVisible = !this.isVisible;
  }
}
</script>

<style scoped>
button {
  margin: 5px;
}
</style>