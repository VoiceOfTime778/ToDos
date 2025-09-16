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
  },
  // дописать оставшиеся пропсы: isCompleted, title
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
