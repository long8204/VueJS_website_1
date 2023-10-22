<template>
  <div class="container">
    <div class="banner">
      <div class="banner-top row d-flex justify-content-center">
        <div class="banner-item col-sm-4 col-11">
          <img src="https://gia-dung-sinh-hoat.daca.vn/debaco/assets/img/banner/img1-top-debaco1.jpg" alt="" />
          <div class="banner-item-description">
            <h5>Top Trending</h5>
            <h3>Table Runners</h3>
            <h3>Collection</h3>
            <h5>Discover Now</h5>
          </div>
        </div>
        <div class="banner-item col-sm-4 col-11">
          <img src="https://gia-dung-sinh-hoat.daca.vn/debaco/assets/img/banner/img1-top-debaco2.jpg" alt="" />
          <div class="banner-item-description">
            <h5>Black Fridays!</h5>
            <h3>Sale up To 50% Off</h3>
            <h3>Dinning Ware</h3>
            <h5></h5>
          </div>
        </div>
        <div class="banner-item col-sm-4 col-11">
          <img src="https://gia-dung-sinh-hoat.daca.vn/debaco/assets/img/banner/img1-top-debaco3.jpg" alt="" />
          <div class="banner-item-description">
            <h5>New Arrivals</h5>
            <h3>Classic</h3>
            <h3>Flatware</h3>
            <h5>Discover Now</h5>
          </div>
        </div>
      </div>
      <div class="banner-bottom row d-flex justify-content-around align-items-center">
        <div class="banner-item col-sm-3 col-12">
          <img src="https://gia-dung-sinh-hoat.daca.vn/debaco/assets/img/icon/free_shipping.png" alt="" />
          <h5>Free Shipping</h5>
          <p>Free shipping all order</p>
        </div>
        <div class="banner-item col-sm-3 col-12">
          <img src="https://gia-dung-sinh-hoat.daca.vn/debaco/assets/img/icon/money_back.png" alt="" />
          <h5>Money Return</h5>
          <p>30 days for free return</p>
        </div>
        <div class="banner-item col-sm-3 col-12">
          <img src="https://gia-dung-sinh-hoat.daca.vn/debaco/assets/img/icon/support247.png" alt="" />
          <h5>Online Support</h5>
          <p>Support 24 hours a day</p>
        </div>
        <div class="banner-item col-sm-3 col-12">
          <img src="https://gia-dung-sinh-hoat.daca.vn/debaco/assets/img/icon/promotions.png" alt="" />
          <h5>Deals & Promotions</h5>
          <p>Price savings discounts</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {}
</script>
<style lang="scss" scoped>
.banner {
  margin-top: 75px !important;

  &>* {
    margin-bottom: 50px;
  }

  .banner-top {
    .banner-item {
      text-align: center;
      position: relative;
      margin-bottom: 10px;
      cursor: pointer;

      img {
        width: 100%;
        transition: opacity 0.5s;

        &:hover {
          opacity: 0.5;
        }
      }

      .banner-item-description {
        position: absolute;
        top: 40px;

        h5 {
          font-family: roboto_light;
          font-size: 18px;

          &:last-of-type {
            font-family: roboto;
            display: inline-block;
            border-bottom: 2px solid red;
          }
        }

        h3 {
          font-size: 26px;

          &:nth-of-type(1) {
            font-family: roboto_med;
            margin-bottom: 3px;
          }

          &:nth-of-type(2) {
            font-family: roboto_light;
          }
        }
      }

      &:first-child .banner-item-description {
        text-align: left;
        left: 50px;
      }

      &:nth-child(2) .banner-item-description {
        text-align: center;
        left: 50%;
        transform: translateX(-47%);
      }

      &:last-child .banner-item-description {
        text-align: left;
        left: 50px;
      }
    }
  }

  .banner-bottom {
    .banner-item {
      text-align: center;
      border-right: 1px solid #ebebeb;
      margin-bottom: 20px;

      &:last-child {
        border-right: none;
      }

      h5 {
        font-size: 17px;
        margin: 10px 0 0 0;
        font-family: roboto_med;
      }

      p {
        font-size: 15px;
        font-family: roboto;
      }
    }
  }
}
</style>
