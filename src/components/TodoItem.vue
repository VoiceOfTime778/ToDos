<template>
  <div class="todo-container">
    <input
      type="checkbox"
      :checked="isCompleted"
      @change="handleChange"
    >
    <p>{{ props.title }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const props=defineProps({
  id: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
  isCompleted: {
    type: Boolean,
    required: true,
  },
})
const emit=defineEmits([
  'toggle',
])

const handleChange=() => {
  // дописать функцию, которая будет сообщать об изменении пропса isCompleted
}
</script>

<style scoped>
.todo-container {
  display: flex;
  border: 1px solid;
  border-color: lightgray;
  gap: 5px;
  max-width: 350px;
}
</style>
