<template>
  <div>
    <post-form v-model="newPost" @post-created="addPost" />
    <div class="post" v-for="post in posts" :key="post.id">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
      <button @click="deletePost(post.id)">Удалить</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    posts: Array, // Принимаем массив постов через props
  },
  methods: {
    deletePost(postId) {
      /* eslint-disable vue/no-mutating-props */
      const index = this.posts.findIndex((post) => post.id === postId);
      if (index !== -1) {
        this.posts.splice(index, 1);
        this.$emit("post-deleted", postId);
      }
      /* eslint-enable vue/no-mutating-props */
    },
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
