<template>
  <Navbar></Navbar>
  <SlideShow :width="'100vw'" :height="'60vh'" :images="slide_images"></SlideShow>
  <Banner></Banner>
  <TrendingProduct></TrendingProduct>
  <Category :img_tall="cate_tall" :img_fat="cate_fat"></Category>
  <TabProduct></TabProduct>
</template>
<script>
// import component
import Navbar from '../components/Navbar_Comp.vue'
import SlideShow from '../components/SlideShow.vue'
import Banner from '../components/Banner_Comp.vue'
import TrendingProduct from '../components/TrendingProduct_Comp.vue'
import Category from '../components/Category_Comp.vue'
import TabProduct from '../components/TabProduct.vue'

import { ref } from 'vue'

// import slide image url
import slide1 from '@/assets/images/SlideShow/slide1.jpg'
import slide2 from '@/assets/images/SlideShow/slide2.jpg'
import slide3 from '@/assets/images/SlideShow/slide3.jpg'
// import category image url
import cate_tall_1 from '@/assets/images/Category/cate_tall_1.jpg'
import cate_tall_2 from '@/assets/images/Category/cate_tall_2.jpg'
import cate_tall_3 from '@/assets/images/Category/cate_tall_3.jpg'
import cate_tall_4 from '@/assets/images/Category/cate_tall_4.jpg'
import cate_fat_1 from '@/assets/images/Category/cate_fat_1.jpg'
import cate_fat_2 from '@/assets/images/Category/cate_fat_2.jpg'

export default {
  components: {
    Navbar,
    SlideShow,
    Banner,
    TrendingProduct,
    Category,
    TabProduct
  },
  setup() {
    const slide_images = ref([slide1, slide2, slide3])
    const cate_tall = ref([cate_tall_1, cate_tall_2, cate_tall_3, cate_tall_4])
    const cate_fat = ref([cate_fat_1, cate_fat_2])

    return { slide_images, cate_tall, cate_fat }
  }
}
</script>
<style lang="scss"></style>
