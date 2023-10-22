<template>
  <div class="container">
    <div class="category row d-flex justify-content-center">
      <div class="category-item col-sm-3 col-4">
        <img :src="img_tall[0]" alt="" />
        <div class="category-item-description">
          <h3>Accessories</h3>
          <h5>Shop Now</h5>
        </div>
      </div>
      <div class="category-item col-sm-6 col-8">
        <img :src="img_fat[0]" alt="" />
        <div class="category-item-description">
          <h3>Accessories</h3>
          <h5>Shop Now</h5>
        </div>
      </div>
      <div class="category-item col-sm-3 col-4">
        <img :src="img_tall[1]" alt="" />
        <div class="category-item-description">
          <h3>Accessories</h3>
          <h5>Shop Now</h5>
        </div>
      </div>
      <div class="category-item col-sm-3 col-4">
        <img :src="img_tall[2]" alt="" />
        <div class="category-item-description">
          <h3>Accessories</h3>
          <h5>Shop Now</h5>
        </div>
      </div>
      <div class="category-item col-sm-3 col-4">
        <img :src="img_tall[3]" alt="" />
        <div class="category-item-description">
          <h3>Accessories</h3>
          <h5>Shop Now</h5>
        </div>
      </div>
      <div class="category-item col-sm-6 col-12">
        <img :src="img_fat[1]" alt="" />
        <div class="category-item-description">
          <h3>Accessories</h3>
          <h5>Shop Now</h5>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    img_tall: Array,
    img_fat: Array
  }
}
</script>

<style lang="scss" scoped>
.category {
  margin-top: 20px;

  .category-item {
    position: relative;
    transition: opacity 0.5s;
    cursor: pointer;

    img {
      width: 100%;
      height: 90%;
    }

    .category-item-description {
      position: absolute;
      top: 15px;
      left: 35px;

      h5 {
        font-family: roboto_light;
        font-size: 14px;
        width: fit-content;

        &:last-of-type {
          font-family: roboto;
          border-bottom: 2px solid red;
        }

      }

      h3 {
        font-size: 22px;

        &:nth-of-type(1) {
          font-family: roboto_med;
          margin-bottom: 3px;
        }

        &:nth-of-type(2) {
          font-family: roboto_light;
        }
      }

      @media (max-width: 577px) {
        & {
          top: 15px;
          left: 25px;
        }

        h5 {
          font-size: 8px;
        }

        h3 {
          margin: 0 0 2px 0 !important;
          font-size: 14px;
        }
      }
    }

    &:hover {
      opacity: 0.5;
    }
  }
}
</style>
