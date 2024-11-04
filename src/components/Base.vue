<template>
  <div :style="baseStyle" class="baseBeverage"></div>
</template>

<script setup lang="ts">
  import { computed } from "vue";
  import { defineProps } from "vue";

  const props = defineProps({
    beverage: {
      type: String,
      required: true
    }
  });

  const baseStyle = computed(() => {
    switch (props.beverage) {
      case "Black Tea":
        return { backgroundColor: "#4C1208" };
      case "Green Tea":
        return { backgroundColor: "#89AB82" };
      case "Coffee":
        return { backgroundColor: "#6F4E37" };
      default:
        return { backgroundColor: "#ffffff" };
    }
  });
  </script>

  <style scoped>
    .baseBeverage {
      position: relative;
      width: 100%;
      height: 100%;
      bottom: 0;
      animation: pour-tea 2s;
      z-index: 300;
      border-radius: 0.05em 0.05em 2.2em 2.2em;
      transition: background-color 0.3s ease;
    }
</style>
