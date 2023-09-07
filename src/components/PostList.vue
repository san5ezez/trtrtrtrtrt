<template>
  <post-form v-model="newPost" @post-created="addPost" />
  <div class="post" v-for="post in posts" :key="post">
    <div><strong>Название:</strong> {{ post.title }}</div>
    <div><strong>Описание:</strong> {{ post.body }}</div>
  </div>
  <div class="post___btns">
    <button>Удалить</button>
  </div>
</template>

<script>
export default {
  props: {
    posts: Array, // Принимаем массив постов через props
  },
};
</script>

<style>
.post {
  margin: 1rem 0;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.post strong {
  color: #ff5733;
}
</style>
