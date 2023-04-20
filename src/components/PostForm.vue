<template>
  <form @submit.prevent>
    <h4>Creating a new post</h4>
    <input v-model="post.title" class="input" type="text" placeholder="Title" />
    <input
      v-model="post.description"
      class="input"
      type="text"
      placeholder="Description"
    />
    <MyButton @click="createPost">Add a new post</MyButton>
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
export default {
  components: {
    MyButton,
  },
  data() {
    return {
      post: {
        title: "",
        description: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        description: "",
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  padding: 10px 15px;
  border: 1px solid teal;
  margin-top: 15px;
}
</style>
