<template>
  <v-app>
    <v-app-bar class="bg-white custom-toolbar">
      <v-container class="d-flex align-center">
        <!-- 左侧 LOGO -->
        <v-img src="./assets/logo-volleycup.png" width="205px" class="logo" />

        <!-- 右侧导航按钮（lg 及以上） -->
        <v-row class="d-none d-md-flex" justify="end">
          <v-btn>Home</v-btn>
          <v-btn>About Us</v-btn>
          <v-btn>Trainings</v-btn>
          <v-btn>Packages</v-btn>
          <v-btn>Blog</v-btn>
          <v-btn>Contact</v-btn>
          <v-btn>Events</v-btn>
        </v-row>

        <!-- 右侧汉堡菜单（lg 以下） -->
        <v-btn icon class="d-flex d-md-none" @click="drawer = true">
          <v-icon>mdi-menu</v-icon>
        </v-btn>
      </v-container>

      <!-- 左侧滑出菜单 -->
      <v-navigation-drawer v-model="drawer" temporary absolute left>
        <v-list>
          <v-list-item v-for="page in pages" :key="page" @click="drawer = false">
            <v-list-item-title>{{ page }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-app-bar>

    <v-main>
      <swiper></swiper>
    </v-main>

    <v-container>
      <v-img id="volleyball" src="./assets/volleyball.png" @load="animateVolleyball"></v-img>
      <v-img id="girl" src="./assets/volleyball-girl.png"></v-img>
    </v-container>
    <v-container>
      <v-img id="girl" src="./assets/volleyball-girl.png"></v-img>
    </v-container>
  </v-app>
</template>f

<script setup>
import { ref, onMounted, nextTick } from 'vue';
import swiper from './components/swiper.vue';
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

const drawer = ref(false);
const pages = ["Home", "About Us", "Trainings", "Packages", "Blog", "Contact", "Events"];

gsap.registerPlugin(ScrollTrigger);

const animateVolleyball = () => {
  const volleyballEl = document.querySelector('#volleyball');
    gsap.to(volleyballEl, {
      rotation: 360,
      duration: 15,
      repeat: -1,
      repeatDelay: 0,
      ease: 'none',
    })
  }

  // const animateGirl = () => {
  // const volleyballEl = document.querySelector('#volleyball');
  //   gsap.to(volleyballEl, {
  //     rotate: 720,
  //     duration: 3,
  //     scrollTrigger: {
  //       trigger: volleyballEl,
  //       start: 'top center',
  //       end: 'top 100px',
  //       scrub: 2,
  //       markers: true
  //     }
  //   })
  // }

onMounted(async () => {
  await nextTick(); // 确保DOM已经渲染完成
  animateVolleyball(); // 仅在挂载后调用以检查是否能找到元素
});
</script>

<style lang="scss" scoped>
:deep(.v-toolbar__content) {
  height: 120px !important;
}
.swiper {
  margin-top: 41px;
}

.bg-white {
  background-color: white;
}

.logo {
  max-height: 64px;
}

.v-application {
  background: #fff;
}

#volleyball {
  width: 700px;
  height: 700px;
  position: absolute;
  opacity: 0.85;
}

#girl {
  width: 500px;
}
</style>
