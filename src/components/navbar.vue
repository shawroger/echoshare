<script setup lang="ts">
import logo from "../assets/navlogo.png"
import titleimg from "../assets/title.png"
import { defineModel } from "vue"

const navColor = "#fff";
const showSidebar = defineModel<number>({ default: 0 });

</script>

<template>
  <VaNavbar :color="navColor" class="mb-3 shadow-md">
    <template #left>
      <VaButton :color="navColor" :icon="showSidebar ? 'menu_open' : 'menu'" @click="showSidebar = (showSidebar+1)%2" />
      <VaNavbarItem>
          <img :src="titleimg" alt="web-logo" class="w-40 max-w-full max-h-full ml-3" />
       
      </VaNavbarItem>
    </template>
    <template #right>
      <VaNavbarItem class="hidden flex-none sm:block">
        <img :src="logo" alt="web-logo" class="w-16 max-w-full max-h-full" />
      </VaNavbarItem>
    </template>
  </VaNavbar>
</template>
