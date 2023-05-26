<template>
  <div v-show="posts.length > 0">
    <h3>List</h3>
    <transition-group name="post-list">
      <PostItem
        v-for="post in posts"
        :post="post"
        :key="post.id"
        @remove="$emit('remove', post)"
      />
    </transition-group>
  </div>
  <h2 v-show="posts.length === 0">List posts empty!</h2>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.post-list-item {
  display: inline-block;
  margin-right: 10px;
}
.post-list-enter-active, .post-list-leave-active {
  transition: all 0.6s;
}
.post-list-enter, .post-list-leave-to  {
  opacity: 0;
  transform: translateX(130px);
}

.post-list-move {
  transition: transform 0.6s;
}
</style>
