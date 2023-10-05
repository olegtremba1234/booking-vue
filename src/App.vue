<script>
import Button from "./components/Button.vue";
import DirectivesTest from "./components/DirectivesTest.vue";
import StarRating from "./components/StarRating.vue";

export default {
  name: "App",
  components: {
    Button,
    DirectivesTest,
    StarRating,
  },
  data() {
    return {
      amountOfClicks: 0,
    };
  },
  computed: {
    title() {
      return ` ${this.amountOfClicks}`;
    },
  },
  methods: {
    increment() {
      this.amountOfClicks += 1;
    },
  },
};
</script>

<template>
  <div class="flex flex-col items-center justify-center">
    <h1>{{ title }}</h1>
    <Button @click="increment">Click me</Button>
    <DirectivesTest />
    <StarRating :rating="4" />
  </div>
</template>
