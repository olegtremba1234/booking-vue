<template>
  <Container>
    <slot name="title"></slot>
    <div class="apartmentsList">
      <template v-for="apartment in items">
        <slot name="apartment" v-bind:apartment="apartment"></slot>
      </template>
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
  margin-left: -15px;
  margin-right: -15px;

  &Item {
    margin-bottom: 30px;
  }
}
</style>
