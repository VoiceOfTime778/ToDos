<template>
  <div class="app">
    <h1 class="title">Список важных дел</h1> <span>Количество незавершенных дел: {{ activeCount }} </span>
    <!-- используя директиву v-for отрисовать список элементов TodoItem.
        1) пробросить значения в props
        2) отслеживать изменения параметра isComplited
    -->
    <TodoItem
      v-for="item in todoItems"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :is-completed="item.isCompleted"
    />
  </div>
</template>

<script setup>
import { ref,computed } from 'vue'
import todos from '@/mocks/todos.js'  // импортируем массив важных дел
import TodoItem from '@/components/TodoItem.vue' // импортируем элемент для отображения, который необходимо доделать

const todoItems=ref(todos)
const activeCount=computed(() => {
  return todoItems.value.filter(item => !item.isCompleted).length
})
</script>

<style scoped>
.title {
  display: block;
}
.app {
  display: block;
  margin-left: auto;
  margin-right: auto;
  max-width: 400px;
}
</style>
