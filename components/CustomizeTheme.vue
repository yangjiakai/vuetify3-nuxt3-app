<!--
* @Component: CustomizeTheme
* @Maintainer: Yang J.K.
* @Description: HomePage
-->
<script setup lang="ts">
import { useCustomizeThemeStore } from "@/stores/customizeTheme";
const customizeTheme = useCustomizeThemeStore();
</script>

<template>
  <div>
    <v-navigation-drawer permanent location="right">
      <div class="ml-5 pa-5">
        <v-switch
          v-model="customizeTheme.darkTheme"
          label="主题切换"
          color="orange"
          hide-details
        ></v-switch>
      </div>
      <v-divider></v-divider>
      <v-btn
        class="ma-5"
        @click.stop="customizeTheme.setMiniSideBar(!customizeTheme.miniSidebar)"
        color="warning"
        >收缩侧面菜单</v-btn
      >
    </v-navigation-drawer>
  </div>
</template>

<style scoped></style>
