<template>
  <button class="my-button">{{ buttonText }}</button>
</template>

<script>
export default {
  props: {
    buttonText: String, // Принимаем текст кнопки через props
  },
};
</script>

<style scoped>
.my-button {
  padding: 0.5rem 1rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

.my-button:hover {
  background-color: #0056b3;
}
</style>
