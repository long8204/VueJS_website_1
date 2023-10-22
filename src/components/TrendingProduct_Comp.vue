<template>
  <div class="container">
    <div class="trending-product">
      <div class="heading">
        <h2>New Treding Products</h2>
        <p>
          Accumsan life at the foot of the swimming pool is like a free body care for each person
        </p>
      </div>
      <div class="product-show row d-flex justify-content-around">
        <div class="col-11 col-sm-3">
          <Product :img="p1" :manufacturer="'Mony'" :name="'Classic ceramics kitchen ware'" :price="90.00" :star="5"
            :new_tag="true" :sale_tag="15">
          </Product>
        </div>
        <div class="col-11 col-sm-3">
          <Product :img="p2" :manufacturer="'Quickiin'" :name="'Origin ceramics kitchen ware'" :price="40.00" :star="3"
            :new_tag="true" :sale_tag="5">
          </Product>
        </div>
        <div class="col-11 col-sm-3">
          <Product :img="p3" :manufacturer="'Quickiin'" :name="'Digital 8th generation gadget'" :price="80.00" :star="4"
            :new_tag="true" :sale_tag="25">
          </Product>
        </div>
        <div class="col-11 col-sm-3">
          <Product :img="p4" :manufacturer="'Mony'" :name="'Classic ceramics kitchen ware'" :price="60.01" :star="1"
            :new_tag="true" :sale_tag="40">
          </Product>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Product from './function/Product_Load.vue'
import p1 from '@/assets/images/Products/p1.jpg'
import p2 from '@/assets/images/Products/p2.jpg'
import p3 from '@/assets/images/Products/p3.jpg'
import p4 from '@/assets/images/Products/p4.jpg'
export default {
  components: {
    Product
  },
  data() {
    return {
      p1,
      p2,
      p3,
      p4
    }
  }
}
</script>
<style lang="scss" scoped>
.trending-product {
  margin-bottom: 50px;

  h2 {
    text-align: center;
    font-family: roboto_med;
  }

  p {
    text-align: center;
    font-family: roboto_light;
    font-style: italic;
    color: rgba(0, 0, 0, 0.623);
  }

  .product-show {
    margin-top: 25px;
  }
}
</style>
