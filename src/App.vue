<template>
  <div id="container" class="w-screen h-screen p-12 grid grid-cols-12 gap-6">
    <ShinyCard class="h-80 col-span-8" />
    <ShinyCard class="h-80 col-span-4" />
    <ShinyCard class="h-80 col-span-6" />
    <ShinyCard class="h-80 col-span-6" />
    <ShinyCard class="h-80 col-span-4" />
    <ShinyCard class="h-80 col-span-8" />
  </div>
</template>

<script setup>
import ShinyCard from "./components/ShinyCard.vue";
</script>
