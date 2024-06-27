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
  </v-app>
</template>

<script setup>
import { ref } from 'vue';
import swiper from './components/swiper.vue';

const drawer = ref(false);

</script>

<style lang="scss" scoped>
.swiper {
  margin-top: 41px;
}

.custom-toolbar,.v-toolbar__content {
  height: 120px !important;
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
</style>
