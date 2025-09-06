<template>
  <div class="font-mono font-bold">
    <Header>Landing Page</Header>
    <main class="text-white p-5 min-h-screen bg-[#121212ff] max-w-[70rem] mx-auto">
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
      <p v-if="pending">loading...</p>
      <div v-else-if="error">
        <p>error: {{ error.message }}</p>
      </div>
      <div v-else>
        <p>{{ data.message }}</p>
        <ul>
          <li v-for="item in data.items" :key="item.id">
            {{ item.name }}
          </li>
        </ul>
      </div>
      <div class="flex flex-col items-center justify-center">
        <p class="my-5">check out my projects</p>
        <ul class="flex flex-wrap gap-5 items-center justify-center">
          <li><NuxtLink to='https://github.com/rho8525/arkez'><Card>Arkez</Card></NuxtLink></li>
          <li><NuxtLink to='https://github.com/rho8525/rhalq'><Card>Rhalq</Card></NuxtLink></li>
          <li><NuxtLink to='https://github.com/rho8525/test'><Card>Test</Card></NuxtLink></li>
        </ul>
      </div>
    </main>
    <Footer />
  </div>
</template>
<script setup lang="ts">
import Header from "../components/Header.vue";
import Card from "../components/Card.vue";
import Footer from "../components/Footer.vue";

function test() {
  alert("testing");
}

const { data, pending, error } = await useFetch("http://localhost:8000/");
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
