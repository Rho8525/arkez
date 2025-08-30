<template>
  <div class="text-white font-mono font-bold">
    <Header />
    <main class="bg-white/10 p-5">
      <div>
        <p class="translate-y-[25px]">hi,</p>
        <p>i'm <span class="name text-5xl">Rho</span>.</p>
      </div>
      <p>self-taught programmer from Indonesia.</p>

      <button
        @click="test"
        class="bg-red-600 w-[100px] h-10 active:scale-[1] hover:scale-[1.1] rounded-md shadow-md shadow-black my-2 p-1"
      >
        test
      </button>
    </main>
    <Footer />
  </div>
</template>
<script setup lang="ts">
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";

function test() {
  alert("testing");
}
</script>
<style scoped>
.name {
  animation: main 2s ease-in-out infinite;
}

@keyframes main {
  0%,
  100%,
  70% {
    color: black;
    filter: drop-shadow(0 0 0 black);
  }
  50%,
  80% {
    color: red;
    filter: drop-shadow(0 0 10px red);
  }
}
</style>
