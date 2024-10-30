<template>
  <div
    ref="target"
    :style="cssVars"
    :class="['rounded-[15px] p-[2px] shine', props.class || '']"
  >
    <div
      class="rounded-[13px] w-full h-full bg-gradient-to-b from-neutral-800/50 to-neutral-950/50 bg-neutral-950/80"
    ></div>
  </div>
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
