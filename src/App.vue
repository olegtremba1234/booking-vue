<script>
import ApartmentsList from "./components/apartment/ApartmentsList.vue";
import apartments from "./components/apartment/apartments";
export default {
  name: "App",
  components: { ApartmentsList },
  data() {
    return {
      apartments,
      apartment: {
        id: "qweqwe",
        title: "Lorem ipsum, dolor sit amet consectetur adipisicing.",
        descr: "Lorem ipsum, dolor sit amet consectetur adipisicing.",
        rating: 4,
        price: 1000,
        location: {
          city: "Kyiv",
        },
        owner: {
          name: "qwe",
          phone: "000-000-0000",
          email: "qwe@qwe.com",
        },
      },
    };
  },
};
</script>

<template>
  <div class="app">
    <ApartmentsList :items="apartments" />
  </div>
</template>

<style lang="scss" scoped>
.app {
  margin-top: 60px;
  text-align: center;
}
</style>
