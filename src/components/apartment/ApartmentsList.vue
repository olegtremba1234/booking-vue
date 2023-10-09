<template>
  <Container>
    <div class="apartmentsList">
      <ApartmentsItem
        v-for="{ id, descr, rating, price, imgUrl } in items"
        :key="id"
        :descr="descr"
        :rating="rating"
        :price="price"
        :imgSrc="imgUrl"
        class="apartmentsListItem"
      />
    </div>
  </Container>
</template>

<script>
import ApartmentsItem from "./ApartmentsItem.vue";
import Container from "../shared/Container.vue";
export default {
  name: "ApartmentsList",
  components: {
    ApartmentsItem,
    Container,
  },
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style lang="scss" scoped>
.apartmentsList {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  /* margin-left: -15px;
  margin-right: -15px; */

  &Item {
    margin-bottom: 30px;
  }
}
</style>
