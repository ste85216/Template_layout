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
      <v-img id="volleyball" src="./assets/volleyball.png"></v-img>
      <v-img id="girl" src="./assets/volleyball-girl.png"></v-img>
    </v-container>
  </v-app>
</template>

<script setup>
import { ref } from 'vue';
import swiper from './components/swiper.vue';
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

const drawer = ref(false);

gsap.registerPlugin(ScrollTrigger);
// const tl = gsap.timeline()
// tl.to('#girl', { x: 2000, duration:2})
// gsap.to('#girl', {
//   x: 1200,
//   duration: 3
// })

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
  width: 800px;
  position: absolute;
  opacity: 0.85;
}

#girl {
  width: 500px;
}
</style>