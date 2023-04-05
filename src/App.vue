<template>
  <div class="app">
    <PostForm />
    <PostList />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "title1", description: "Description1" },
        { id: 2, title: "title2", description: "Description2" },
        { id: 3, title: "title3", description: "Description3" },
      ],
      title: "",
      description: "",
    };
  },
  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        description: this.description,
      };
      this.posts.push(newPost);
      this.title = "";
      this.description = "";
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.app {
  padding: 20px;
}
</style>
