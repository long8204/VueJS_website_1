<template>
  <div class="product">
    <div class="product-header" @mouseenter="show = true" @mouseleave="show = false">
      <img :src="img" alt="" />
      <ul class="product-tag">
        <li v-if="new_tag" class="new-tag">New</li>
        <li v-if="sale_tag > 0" class="sale-tag">- {{ sale_tag }}%</li>
      </ul>
      <button :class="{ show: show }" class="add_cart_btn">Add To Cart</button>
      <transition name="fade" appear>
        <ul class="product-options d-flex flex-column">
          <li :class="{ show: show }"><i class="bi bi-heart"></i></li>
          <li :class="{ show: show }"><i class="bi bi-arrow-repeat"></i></li>
          <li :class="{ show: show }"><i class="bi bi-search"></i></li>
        </ul>
      </transition>
    </div>
    <div class="product-body">
      <div class="row">
        <div class="col-7 product-manufacturer">
          <p>{{ manufacturer }}</p>
        </div>
        <div class="col-5 product-rate">
          <i v-for="i in star" :key="i" class="bi bi-star-fill"></i>
          <i v-for="i in 5 - star" :key="i" class="bi bi-star"></i>
        </div>
      </div>
      <div class="color-select d-flex">
        <ul>
          <li><a style="background-color: rgb(147, 180, 252)"></a></li>
          <li><a style="background-color: rgb(252, 241, 147)"></a></li>
          <li><a style="background-color: rgb(100, 100, 100)"></a></li>
          <li><a style="background-color: rgb(182, 114, 69)"></a></li>
        </ul>
      </div>
      <div class="product-name">
        <p>{{ name }}</p>
      </div>
      <div class="product-price">
        <h4>${{ salePrice }}</h4>
        <h5 v-if="sale_tag > 0">${{ price }}</h5>
      </div>
    </div>
    <div class="product-bottom"></div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      show: false,
    }
  },
  props: {
    new_tag: Boolean,
    sale_tag: Number,
    manufacturer: String,
    img: String,
    name: String,
    price: Number,
    star: Number
  },
  methods: {},
  computed: {
    salePrice() {
      return (this.price - this.price / 100 * this.sale_tag).toFixed(2);
    }
  },
}
</script>
<style lang="scss" scoped>
.show {
  display: block !important;
  animation: fade 0.75s;
}

.product {
  margin-bottom: 40px;

  .product-header {
    position: relative;
    cursor: pointer;

    img {
      width: 100%;
    }

    .product-tag {
      position: absolute;
      top: 10px;
      left: 10px;
      display: flex;
      flex-direction: column;
      font-size: 12px;

      &>* {
        width: 100%;
        margin-bottom: 5px;
        text-align: center;
        padding: 2px 15px;
        border-radius: 2px;
        color: white;
        font-family: roboto;
      }

      .new-tag {
        background-color: red;
      }

      .sale-tag {
        background-color: black;
      }
    }

    .add_cart_btn {
      position: absolute;
      bottom: 10px;
      left: 50%;
      transform: translateX(-50%);
      display: none;
      background-color: white;
      border: none;
      border-radius: 40px;
      padding: 7px 20px;
      box-shadow:
        rgba(60, 64, 67, 0.3) 0px 1px 2px 0px,
        rgba(60, 64, 67, 0.15) 0px 1px 3px 1px;
      animation: fade 0.75s;
    }

    .product-options {
      position: absolute;
      top: 10px;
      right: 10px;

      li {
        padding: 13px 13px;
        box-shadow:
          rgba(0, 0, 0, 0.1) 0px 0px 5px 0px,
          rgba(0, 0, 0, 0.1) 0px 0px 1px 0px;
        background-color: white;
        margin-bottom: 8px;
        border-radius: 50%;
        line-height: 1;
        cursor: pointer;
        display: none;
      }
    }
  }

  .product-body {
    .product-manufacturer {
      margin-top: 5px;
      font-size: 14px;
      font-family: roboto_light;
    }

    .product-rate {
      margin-top: 5px;
      font-size: 14px;
      font-family: roboto_light;
      text-align: right;
      color: gold;

      &>* {
        margin-left: 1px;
      }
    }

    .color-select {
      margin-top: 10px;

      ul li {
        padding: 1px;
        border: 1px solid rgb(204, 204, 204);
        border-radius: 1px;
        display: inline-block;
        margin-right: 7px;

        a {
          width: 15px;
          height: 15px;
          display: block;
        }
      }
    }

    .product-name {
      font-family: roboto_med;
      font-size: 17px;
    }

    .product-price {
      &>* {
        display: inline;
      }

      h4 {
        margin-top: 5px;
        color: rgb(235, 56, 56);
        font-family: roboto_med;
      }

      h5 {
        margin-left: 10px;
        color: rgba(109, 109, 109, 0.637);
        text-decoration: line-through;
        font-family: roboto;
      }
    }
  }
}

@keyframes zoom-out {
  from {
    transform: translateX(-50%) scale(0);
  }

  to {
    transform: translateX(-50%) scale(1);
  }
}

@keyframes fade {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
</style>
