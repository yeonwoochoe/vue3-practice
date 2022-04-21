<template>
  <div :class="{ large }" :style="{ backgroundColor: color }" class="btn">
    <!-- {{ text }} -->

    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: "gray",
    },
    large: {
      type: Boolean,
      default: false,
    },
    text: {
      type: String,
      default: "",
    },
  },
};
</script>
<style lang="scss" scoped>
.btn {
  display: inline-block;
  margin: 4px;
  padding: 6px 12px;
  border-radius: 4px;
  background-color: gray;
  color: white;
  cursor: pointer;
  &.large {
    font-size: 15px;
    padding: 15px;
    font-weight: 800;
  }
}
</style>
