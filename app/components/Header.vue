<template>
  <div class="z-[9] sticky top-0 text-white">
    <header class="flex items-center justify-between p-5 bg-black/70">
      <slot />
      <div class="flex gap-5">
        <NuxtLink to="https://github.com/rho8525/arkez">
          <NuxtImg class="invert" src="github.png" width="25" height="25" />
        </NuxtLink>
        <button class="relative z-[99]" @click="menu">
          <span v-if="isOpen">close</span><span v-else>menu</span>
        </button>
      </div>
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
