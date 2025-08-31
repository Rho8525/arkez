<template>
  <div class="font-mono font-bold">
    <Header />
    <main class="text-white bg-white/10 p-5">
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
      <p class="my-5">check out my projects</p>
      <ul class="flex gap-5 items-center justify-center">
        <li>
          <Card>Arkez</Card>
        </li>
        <li><Card>Test</Card></li>
      </ul>
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
