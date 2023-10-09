<script>
import ApartmentsItem from "./components/apartment/ApartmentsItem.vue";
import ApartmentsList from "./components/apartment/ApartmentsList.vue";
import apartments from "./components/apartment/apartments";
export default {
  name: "App",
  components: { ApartmentsList, ApartmentsItem },
  data() {
    return {
      apartments,
    };
  },
};
</script>

<template>
  <div class="app">
    <ApartmentsList :items="apartments">
      <template v-slot:title>New title</template>
      <template v-slot:apartment="{ apartment }">
        <ApartmentsItem
          :key="apartment.id"
          :descr="apartment.descr"
          :rating="apartment.rating"
          :price="apartment.price"
          :imgSrc="apartment.imgUrl"
        />
      </template>
    </ApartmentsList>
  </div>
</template>

<style lang="scss" scoped>
.app {
  margin-top: 60px;
  text-align: center;
}
</style>
