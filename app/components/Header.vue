<template>
  <div class="sticky top-0 text-white">
    <header class="flex items-center justify-between p-5 bg-black/70">
      <slot />
      <div class="flex gap-5">
        <NuxtLink to="https://github.com/rho8525/arkez">
          <NuxtImg class="invert" src="github.png" width="25" height="25" />
        </NuxtLink>
        <button class="relative z-[99]" @click="menu">
          <span v-if="isOpen">clos</span><span v-else>menu</span>
        </button>
      </div>
      <!-- <div
        :class="[
          'z-[9] transition-all duration-300 fixed w-screen left-0 top-0 bg-black/50',
          isOpen ? 'h-1/2 opacity-100' : 'h-0 opacity-0',
        ]"
      ></div>
      <div
        :class="[
          'transition-all duration-300 fixed w-screen left-0 bottom-0 bg-black/50',
          isOpen ? 'h-1/2 opacity-100' : 'h-0 opacity-0',
        ]"
      ></div> -->
      <nav
        :class="[
          'transition-all duration-300 rounded-[0_0_20px_20px] overflow-hidden w-[10rem] absolute bg-black/70 top-[65px] right-0 mx-[100px]',
          isOpen ? 'p-5 h-[20rem]' : 'p-0 h-0',
        ]"
      >
        <ul
          class="relative z-[99] w-full h-full flex flex-col gap-5 items-center justify-start"
        >
          <li><NuxtLink to="/">Root</NuxtLink></li>
          <li><NuxtLink to="/home">Home</NuxtLink></li>
          <li><NuxtLink to="/about">About</NuxtLink></li>
        </ul>
      </nav>
    </header>
  </div>
</template>
<script setup lang="ts">
import { ref } from "vue";

let isOpen = ref(false);

function menu() {
  isOpen.value = !isOpen.value;
}
</script>
