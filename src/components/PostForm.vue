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
    <button class="btn" @click="createPost">Add a new post</button>
  </form>
</template>

<script>
export default {
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

.btn {
  margin-top: 15px;
  padding: 10px 15px;
  align-self: flex-end;
  background: none;
  color: teal;
  border: 1px solid teal;
  border-radius: 25px;
  cursor: pointer;
}

.btn:hover {
  background: teal;
  color: white;
}
</style>
