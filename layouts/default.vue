<!--
* @Maintainer: J.K. Yang
* @Description: Default Layout
-->
<script setup lang="ts">
import { useCustomizeThemeStore } from "@/stores/customizeTheme";
import { ref } from "vue";
const order = ref(1);
const navDrawer = ref(true);
const customizeTheme = useCustomizeThemeStore();
</script>
<template>
  <div>
    <v-app :theme="customizeTheme.darkTheme ? 'dark' : 'light'">
      <!-- APP BAR -->
      <v-app-bar app :order="order">
        <v-app-bar-nav-icon @click.stop="navDrawer = !navDrawer">
        </v-app-bar-nav-icon>
        App Bar
      </v-app-bar>
      <!-- Navigation Drawer -->
      <v-navigation-drawer
        elevation="4"
        v-model="navDrawer"
        :rail="customizeTheme.miniSidebar"
      >
        <v-list density="compact" nav>
          <v-list-item
            prepend-icon="mdi-folder"
            title="My Files"
            value="myfiles"
          ></v-list-item>
          <v-list-item
            prepend-icon="mdi-account-multiple"
            title="Shared with me"
            value="shared"
          ></v-list-item>
          <v-list-item
            prepend-icon="mdi-star"
            title="Starred"
            value="starred"
          ></v-list-item>
        </v-list>
      </v-navigation-drawer>
      <!-- Main -->
      <v-main class="bg-grey-lighten-3">
        <v-container fluid class="h-full">
          <slot />
        </v-container>
      </v-main>
      <!-- Footer -->
      <v-footer app height="72" elevation="5"> Footer </v-footer>
      <CustomizeTheme />
    </v-app>
  </div>
</template>

<style scoped lang="scss"></style>
