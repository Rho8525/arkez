<template>
  <div
    class="text-white w-[25rem] bg-black border p-2 pb-0 hover:shadow-lg hover:shadow-black hover:-translate-y-2 transition-all duration-500"
  >
    <NuxtImg
      class="border w-full"
      src="arkez.png"
      alt="arkez"
      width="1920"
      height="1080"
    />
    <p
      class="text-3xl bg-gradient-to-b from-black/0 via-black to-black -translate-y-5"
    >
      <NuxtLink to="#"><slot /></NuxtLink>
    </p>
  </div>
</template>
