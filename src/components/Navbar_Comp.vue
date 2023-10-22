<template>
  <div class="navbar" :class="{ 'fixed': isFixed, 'show': showNavbar }" @animationend="clearAnimation">
    <div class="container">
      <div class="nav-left d-flex align-items-center">
        <h2 class="brand">WEB 3</h2>
        <ul class="nav-item-list">
          <li class="nav-item">HOME</li>
          <li class="nav-item nav-item-dropdown">
            PAGES
            <ul class="dropdown-menu">
              <li>
                <router-link to="#">Drop_1</router-link>
              </li>
              <li>
                <router-link to="#">Drop_2</router-link>
              </li>
              <li>
                <router-link to="#">Drop_3</router-link>
              </li>
            </ul>
          </li>
          <li class="nav-item">SHOP</li>
          <li class="nav-item nav-item-dropdown">
            BLOG
            <ul class="dropdown-menu">
              <li>
                <router-link to="#">Drop_1</router-link>
              </li>
              <li>
                <router-link to="#">Drop_2</router-link>
              </li>
              <li>
                <router-link to="#">Drop_3</router-link>
              </li>
            </ul>
          </li>
          <li class="nav-item">CONTACT US</li>
        </ul>
      </div>
      <div class="nav-center">
      </div>
      <div class="nav-right">
        <i class="bi bi-search"></i>
        <i class="bi bi-person"></i>
        <i class="bi bi-heart">
          <div class="favorite">20</div>
        </i>
        <i class="bi bi-cart">
          <div class="cart">10</div>
        </i>
      </div>
    </div>
  </div>
</template>
<script>
import $ from "jquery";
$(document).ready(function () {
  $('.nav-item-dropdown').append('<i style="font-size: 12px; margin-left: 5px" class="bi bi-chevron-down"></i>');
});
export default {
  data() {
    return {
      isFixed: false,
      showNavbar: false,
    };
  },
  methods: {
    clearAnimation() {
      this.showNavbar = false;
    },
    handleScroll() {
      if (window.scrollY > 100 && !this.isFixed) {
        this.isFixed = true;
        this.showNavbar = true;
      } else if (window.scrollY <= 100 && this.isFixed) {
        this.isFixed = false;
        this.showNavbar = false;
      }
    },
  },
  created() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() { // Use beforeUnmount instead of beforeDestroy
    window.removeEventListener('scroll', this.handleScroll);
  },
};
</script>
<style lang="scss" scoped>
.fixed {
  position: fixed;
  z-index: 999;
  background-color: white;
  width: 100vw;
  height: 65px !important;
  box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px, rgba(60, 64, 67, 0.15) 0px 2px 6px 2px;
}

.show {
  animation: appearance 0.5s;
}

.navbar {
  height: 100px;

  .nav-left {
    .brand {
      display: inline;
      margin-right: 70px;
      font-family: roboto_bold;
    }

    ul {
      li {
        font-family: roboto_med;
        margin-right: 30px;
      }
    }

    @media (max-width: 768px) {
      .nav-item-list {
        display: none;
      }
    }
  }

  .nav-right {
    i {
      margin-right: 20px;
      font-size: 20px;
      position: relative;
      cursor: pointer;

      &:hover {
        transform: scale(1.1);
      }
    }

    .favorite,
    .cart {
      position: absolute;
      top: -5px;
      left: 10px;
      font-family: roboto;
      font-style: normal;
      font-size: 10px;
      width: 18px;
      height: 18px;
      text-align: center;
      background-color: rgb(223, 2, 2);
      color: white;
      padding-top: 1px;
      border-radius: 50%;
    }
  }
}

.nav-item-dropdown {
  position: relative;
  transition: color 1s ease;

  &:hover .dropdown-menu {
    display: block;
    animation-name: appearance;
    animation-duration: 0.3s;
    animation-fill-mode: forwards;
  }

  .dropdown-menu {
    li {
      display: block !important;
      margin-bottom: 10px;
      padding: 5px;

      a {
        color: rgb(0, 0, 0);
        transition: color 0.3s ease;

        &:hover {
          color: red;
        }
      }
    }

    position: absolute;
    top: 61px;
    left: 0;
    background-color: rgb(255, 255, 255);
    border: 1px solid rgb(224, 224, 224);
    padding: 20px 20px 20px 10px !important;
    border-radius: 1px;
    display: none;
  }
}

@keyframes appearance {
  from {
    opacity: 0;
  }

  to {
    display: 1;
  }
}
</style>