<template>
  <div class="app">
    <form @submit.prevent>
      <h4>Creating a new post</h4>
      <input
        v-bind:value="title"
        @input="title = $event.target.value"
        class="input"
        type="text"
        placeholder="Title"
      />
      <input
        v-bind:value="description"
        @input="description = $event.target.value"
        class="input"
        type="text"
        placeholder="Description"
      />
      <button class="btn" @click="createPost">Add a new post</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Title: </strong>{{ post.title }}</div>
      <div><strong>Description: </strong>{{ post.description }}</div>
    </div>
    <div>
      <button class="btn" @click="addLike">Like</button>
      <button class="btn" @click="addDislike">Dislike</button>
    </div>
    <div>
      Number of likes: <strong>{{ likes }}</strong>
    </div>
    <div>
      Number of dislikes: <strong>{{ dislikes }}</strong>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        { id: 1, title: "title1", description: "Description1" },
        { id: 2, title: "title2", description: "Description2" },
        { id: 3, title: "title3", description: "Description3" },
      ],
      title: "",
      description: "",
      likes: 0,
      dislikes: 0,
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
    },
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislikes += 1;
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

.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

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
