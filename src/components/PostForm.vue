<template>
  <div>
    <form @submit.prevent="createPost">
      <h4>Создание поста</h4>
      <input
        class="input"
        type="text"
        placeholder="Название"
        v-model="newPost.title"
      />
      <input
        class="input"
        type="text"
        placeholder="Описание"
        v-model="newPost.body"
      />
      <button type="submit">Создать</button>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: Object, // Принимаем объект newPost через props
  },
  data() {
    return {
      newPost: {
        title: "",
        body: "",
      },
    };
  },
  watch: {
    modelValue: {
      handler(newValue) {
        this.newPost = { ...newValue };
      },
      immediate: true,
    },
  },
  methods: {
    createPost() {
      this.$emit("post-created", { ...this.newPost }); // Объявляем событие post-created
      this.newPost.title = "";
      this.newPost.body = "";
    },
  },
};
</script>

<style>
.input {
  margin: 0.5rem 0;
  padding: 0.3rem;
  width: 100%;
  border: 1px solid #ccc;
  border-radius: 4px;
}

#button {
  padding: 0.3rem 1rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
