<template>
  <select v-on="modelValue" @change="changeOption" class="select">
    <option disabled value="">Select in list</option>
    <option 
      v-for="option in options" 
      :key="option.value"
      :value="option.value">
      {{ option.name }}
    </option>
  </select>
</template>

<script>
export default {
  name: "my-select",
  props: {
    modelValue: {
      type: String,
    },
    options: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    changeOption(event) {
      this.$emit('update:modelValue', event.target.value);
    },
  },
};
</script>

<style scoped>
.select{
  padding: 15px 35px;
  border-radius: 25px;
}
</style>
