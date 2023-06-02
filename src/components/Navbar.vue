<template>
  <div class="navbar">
    <div @click="$router.push('/')">App vue</div>
    <div class="navbar__btns">
      <my-button @click="$router.push('/posts')">Posts</my-button>
      <my-button @click="$router.push('/about')" style="margin-left: 20px;">About</my-button>
    </div>
  </div>
</template>

<script>
</script>

<style scoped>
.navbar{
  height: 50px;
  background-color: turquoise;
  box-shadow: 2px 2px 4px teal;
  display: flex;
  padding: 0 15px;
  align-items: center;
}

.navbar__btns{
  margin-left: auto;
}
</style>