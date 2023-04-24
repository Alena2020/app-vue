<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-button",
};
</script>

<style scoped>
.btn {
  margin-top: 15px;
  padding: 10px 15px;
  align-self: flex-end;
  background: none;
  color: #2ba7dd;
  border: 1px solid #2ba7dd;
  box-shadow: 2px 2px 2px aqua;
  border-radius: 25px;
  cursor: pointer;
}

.btn:hover {
  background: #2ba7dd;
  box-shadow: 2px 2px 2px #1b727f, inset -1px -15px 15px midnightblue;
  color: white;
}
</style>
