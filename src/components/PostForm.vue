<template>
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
</template>

<script></script>

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
