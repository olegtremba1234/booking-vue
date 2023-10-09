<template>
  <div class="apartmentsItem">
    <div class="apartmentsItemInner">
      <img :src="imgSrc" alt="" class="apartmentsItemPhoto" />
      <div class="apartmentsItemContent">
        <p class="apartmentsItemDescription">{{ descr }}</p>
        <div class="apartmentsItemRating">
          <StarRating :rating="rating" />
        </div>
        <div class="apartmentsItemPrice">UAH {{ price }}</div>
      </div>
    </div>
  </div>
</template>

<script>
import StarRating from "../StarRating.vue";
export default {
  name: "ApartmentsItem",
  components: {
    StarRating,
  },
  props: {
    descr: {
      type: String,
      default: "",
    },
    rating: {
      type: Number,
      default: 0,
    },
    price: {
      type: Number,
      required: true,
    },
    imgSrc: {
      type: String,
      default: "",
    },
  },
};
</script>

<style lang="scss" scoped>
.apartmentsItem {
  position: relative;
  max-width: 350px;
  padding: 0 15px;
  margin-bottom: 30px;

  &Inner {
    position: relative;
  }

  &Content {
    position: relative;
    padding: 20px;
    opacity: 0;
    transition: opacity 0.4s;
    background: rgba(#0f1d2d, 0.7);
    min-height: 200px;
    color: #fff;
    line-height: 1.4;
    text-align: left;
    cursor: pointer;
    z-index: 1;

    &:hover {
      opacity: 1;
    }
  }

  &Description {
    margin-bottom: 20px;
    min-height: calc(1em * 1.4 * 3);
    overflow: hidden;
  }

  &Rating {
    margin-bottom: 20px;
  }

  &Price {
    font-size: 20px;
    font-weight: 600;
  }

  &Photo {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
</style>
