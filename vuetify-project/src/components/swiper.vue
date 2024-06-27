<template>
  <swiper 
  :navigation="{
    nextEl: '.swiper-button-next',
    prevEl: '.swiper-button-prev',
  }" 
  :pagination="{
        el: '.swiper-pagination',
        clickable: true,
      }"
  :autoplay="{
    delay: 2500,
    disableOnInteraction: false
  }" 
  :loop="true" 
  :modules="modules" 
  class="mySwiper">
    <swiper-slide><img src="https://picsum.photos/1920/700/?random=1"></swiper-slide>
    <swiper-slide><img src="https://picsum.photos/1920/700/?random=2"></swiper-slide>
    <swiper-slide><img src="https://picsum.photos/1920/700/?random=3"></swiper-slide>
    <swiper-slide><img src="https://picsum.photos/1920/700/?random=4"></swiper-slide>
    <swiper-slide><img src="https://picsum.photos/1920/700/?random=5"></swiper-slide>
    <swiper-slide><img src="https://picsum.photos/1920/700/?random=6"></swiper-slide>
    <swiper-slide><img src="https://picsum.photos/1920/700/?random=7"></swiper-slide>
    <swiper-slide><img src="https://picsum.photos/1920/700/?random=8"></swiper-slide>
    <div class="swiper-button-next"></div>
    <div class="swiper-button-prev"></div>
    <div class="swiper-pagination"></div>
  </swiper>
</template>
<script>
  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css/bundle';

  import 'swiper/css/navigation';
  import 'swiper/css/pagination';


  // import required modules
  import { Autoplay, Navigation, Pagination } from 'swiper/modules';

  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      return {
        modules: [Autoplay, Navigation, Pagination],
      };
    },
  };
</script>

<style lang="scss" scoped>
  .swiper-button-next,
  .swiper-button-prev {
    width: 60px;
    height: 60px;
    color: white;
    background-color: #256fbb;
    border-radius: 50%;
    transition: 0.8s;
  }
  .swiper-button-next::after,
  .swiper-button-prev::after {
  font-size: 18px; /* 縮小箭頭大小 */
  font-weight: 900; 
  }
  .swiper-button-prev::after {
    position: absolute;
    left: 23px;
  }
  .swiper-button-next:hover,
  .swiper-button-prev:hover {
    background: rgb(223, 203, 22);
  }
  .swiper-pagination-bullet {
  width: 20px; /* 改變點點的寬度 */
  height:20px; /* 改變點點的高度 */
  background-color: #000; /* 改變點點的背景顏色 */
  opacity: 1; /* 讓點點不透明 */
}
</style>
