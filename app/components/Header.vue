<template>
  <header
    class="h-[3rem] flex items-center justify-between bg-white/10 p-5 hover:bg-white/20 transition-all duration-300"
  >
    <p>this is header</p>
    <div class="flex gap-5 items-center justify-center">
      <NuxtLink to="https://github.com/rho8525/arkez">
        <NuxtImg
          class="invert"
          src="github.png"
          alt="github"
          width="25"
          height="25"
        />
      </NuxtLink>
      <button @click="menu">menu</button>
    </div>
  </header>
  <nav
    :class="[
      'top-10 right-0 px-5 bg-white/20 overflow-hidden transition-all duration-300 ease-in',
      isOpen ? 'h-[20rem] py-5' : 'py-0 h-0',
    ]"
  >
    <ul class="flex flex-col gap-2 items-center justify-center">
      <li>test</li>
      <li>test</li>
    </ul>
  </nav>
</template>
<script setup lang="ts">
import { ref } from "vue";

let isOpen = ref(false);

function menu() {
  isOpen.value = !isOpen.value;
}
</script>
