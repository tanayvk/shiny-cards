<template>
  <div :class="['bg-neutral-950', props.class || '']"></div>
</template>

<script setup>
const props = defineProps(["class"]);
</script>
