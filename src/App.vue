<script>
import ApartmentsItem from "./components/apartment/ApartmentsItem.vue";
export default {
  name: "App",
  components: { ApartmentsItem },
  data() {
    return {
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
  <div class="flex flex-col items-center justify-center">
    <ApartmentsItem
      :descr="apartment.descr"
      :price="apartment.price"
      :rating="apartment.rating"
      imgSrc="https://mayak.kiev.ua/sites/mayak.kiev/files/news/taunkhaus.jpg"
    />
  </div>
</template>
