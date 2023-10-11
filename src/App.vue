<script>
import ApartmentsItem from "./components/apartment/ApartmentsItem.vue";
import ApartmentsList from "./components/apartment/ApartmentsList.vue";
import CustomInput from "./components/shared/CustomInput.vue";
import apartments from "./components/apartment/apartments";
export default {
  name: "App",
  components: { ApartmentsList, ApartmentsItem, CustomInput },
  data() {
    return {
      text: "",
      apartments,
    };
  },
  methods: {
    handleItemClick() {
      console.log("item clicked");
    },
  },
};
</script>

<template>
  <div class="app">
    <h2>{{ text }}</h2>
    <CustomInput v-model="text" />
    <!-- <input type="text" v-model="text" /> -->
    <ApartmentsList :items="apartments">
      <template v-slot:title>New title</template>
      <template v-slot:apartment="{ apartment }">
        <ApartmentsItem
          :key="apartment.id"
          :descr="apartment.descr"
          :rating="apartment.rating"
          :price="apartment.price"
          :imgSrc="apartment.imgUrl"
          @click="handleItemClick"
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
