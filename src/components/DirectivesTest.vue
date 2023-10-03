<script>
export default {
  name: "DirectivesTest",
  data() {
    return {
      isVisible: true,
      fruits: ["kiwi", "banana", "apple"],
      cars: {
        audi: {
          color: "red",
        },
        bmw: {
          color: "white",
        },
      },
    };
  },
};
</script>

<template>
  <div v-if="isVisible">
    <h2>Directives</h2>
    <ul>
      <template v-for="fruit in fruits">
        <li v-if="fruit === 'banana'" :key="fruit">{{ fruit }}</li>
      </template>
    </ul>
    <ul>
      <li v-for="(car, key) in cars" :key="car.color">{{ key }}</li>
    </ul>
    <ul>
      <li v-for="car in cars" :key="car.color">{{ car.color }}</li>
    </ul>
  </div>
</template>

<style lang="scss" scoped></style>
