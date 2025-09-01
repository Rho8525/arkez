<template>
  <div class="text-white">
    <Header>Arkez</Header>
    <main class="min-h-screen max-w-[70rem] mx-auto">
      <div class="flex flex-col h-screen items-center justify-center">
        <p class="text-3xl">Arkez</p>
        <p>a media of learning for rho, created using nuxtjs</p>
      </div>
    </main>
    <Footer />
  </div>
</template>

<script setup lang="ts">
import Header from "../../components/Header.vue";
import Footer from "../../components/Footer.vue";
</script>
