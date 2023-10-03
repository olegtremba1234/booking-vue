<script>
export default {
  name: "Button",
  props: {
    type: {
      type: String,
      default: "button",
    },
    outlined: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<template>
  <button
    v-on="$listeners"
    v-bind:type="type"
    :class="{ btn: true, btnOutlined: outlined }"
  >
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
.btn {
  display: inline-block;
  font-size: 18px;
  background: #ff662d;
  color: #fff;
  cursor: pointer;
  min-width: 220px;
  border: 1px solid transparent;
  padding: 8px 15px;
  &:hover {
    background: #f26139;
    color: #fff;
  }
  &:focus,
  &:focus-visible {
    outline: 4px auto -webkit-focus-ring-color;
  }
  &Outlined {
    background: none;
    border: 1px solid #ff662d;
    color: #ff662d;
  }
}
</style>
