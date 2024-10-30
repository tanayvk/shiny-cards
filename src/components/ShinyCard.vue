<template>
  <div
    ref="target"
    :style="cssVars"
    :class="['shine bg-neutral-950', props.class || '']"
  ></div>
</template>

<script setup>
import { ref, computed } from "vue";
import { useMouseInElement } from "@vueuse/core";
const props = defineProps(["class"]);
const target = ref(null);
const { elementX, elementY } = useMouseInElement(target);
const cssVars = computed(() => ({
  "--x": `${target.value ? elementX.value : -1000}px`,
  "--y": `${target.value ? elementY.value : -1000}px`,
}));
</script>

<style scoped>
.shine {
  background-image: radial-gradient(
    300px circle at var(--x) var(--y),
    #6366f1 0,
    transparent 100%
  );
}
</style>
