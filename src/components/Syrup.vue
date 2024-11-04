<template>
  <div :style="syrupStyle" class="syrup"></div>
</template>

<script setup lang="ts">
  import { computed } from "vue";
  import { defineProps } from "vue";

  const props = defineProps({
    syrup: {
      type: String,
      required: true
    }
  });

  const syrupStyle = computed(() => {
    switch (props.syrup) {
      case "Vanilla":
        return { backgroundColor: "#F3E5AB" };
      case "Caramel":
        return { backgroundColor: "#8C6028" };
      case "Hazelnut":
        return { backgroundColor: "#AE9F80" };
      default:
        return { backgroundColor: "#c6c6c6" };
    }
  });
</script>

<style lang="scss" scoped>
  .syrup {
    transform: translateY(400%);
    position: relative;
    width: 100%;
    height: 20%;
    animation: pour-tea 2s 1s forwards;
    z-index: 2;
  }
</style>
