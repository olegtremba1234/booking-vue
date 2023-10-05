<script>
export default {
  name: "StarRating",
  props: {
    rating: {
      type: Number,
      default: 0,
    },
    starLimit: {
      type: Number,
      default: 5,
    },
  },
  computed: {
    ratingWidth() {
      return (this.rating / this.starLimit) * 100;
    },
    ratingWidthStyle() {
      return `width: ${this.ratingWidth}%;`;
    },
  },
};
</script>

<template>
  <div class="starRating">
    <span
      v-for="index in starLimit"
      :key="index"
      class="star starOutlined"
    ></span>
    <div class="starRatingColored" :style="ratingWidthStyle">
      <span
        v-for="index in starLimit"
        :key="index"
        class="star starColored"
      ></span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.starRating {
  position: relative;
  display: inline-flex;
  &Colored {
    display: inline-flex;
    position: absolute;
    width: 0;
    height: 100%;
    top: 0;
    left: 0;
    overflow: hidden;
  }
}

.star {
  display: inline-block;
  width: 16px;
  height: 16px;
  margin: 0 3px;
  flex-shrink: 0;
  &Colored {
    background: url("/img/star-filled.svg") center no-repeat;
  }
  &Outlined {
    background: url("/img/star-outlined.svg") center no-repeat;
  }
}
</style>
