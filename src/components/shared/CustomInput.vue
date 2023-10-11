<template>
  <input v-bind="$attrs" class="customInput" v-model="inputValue" />
</template>

<script>
export default {
  name: "CustomInput",
  props: {
    value: String,
  },
  data() {
    return {
      inputValue: this.value,
    };
  },
  //   methods: {
  //     inputChanged(event) {
  //       this.$emit("input", event.target.value);
  //     },
  //   },
  //   computed: {
  //     listeners() {
  //       return {
  //         ...this.$listeners,
  //         input: this.inputChanged,
  //       };
  //     },
  //   },
};
</script>

<style lang="scss" scoped>
@import "../../assets/vars";
.customInput {
  min-height: 40px;
  border: 2px solid $main-color;
  font-size: 18px;
  outline: none;
  line-height: inherit;
  padding: 8px 15px;
}
</style>
