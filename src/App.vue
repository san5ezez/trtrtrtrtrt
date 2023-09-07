<template>
  <div>
    <post-form v-model="newPost" @post-created="addPost" />
    <post-list :posts="posts" />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "Первый", body: "Текст первого поста" },
        { id: 2, title: "Второй", body: "Текст второго поста" },
      ],
      newPost: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    addPost(newPost) {
      const id = this.posts.length + 1;
      this.posts.push({ id, ...newPost });
    },
  },
};
</script>
