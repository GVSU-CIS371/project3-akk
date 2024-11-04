<template>
  <div :style="frothStyle" class="froth">
    <div v-for="n in 5" :key="n" class="foam" :style="foamStyle(n)"></div>
  </div>
</template>

<script setup lang="ts">
  import { computed } from "vue";
  import { defineProps } from "vue";

  const props = defineProps({
    creamer: {
      type: String,
      required: true
    }
  });

  const frothStyle = computed(() => {
    return { backgroundColor: "#c6c6c6" };
  });

  const foamStyle = (index) => {
    switch (props.creamer) {
      case "Milk":
        return { backgroundColor: "#f0e6d2" };
      case "Cream":
        return { backgroundColor: "#e4d2b0" };
      case "Half & Half":
        return { backgroundColor: "#f0d6c4" };
      default:
        return { backgroundColor: "#c6c6c6" };
    }
  };
</script>

<style lang="scss" scoped>
  .froth {
    overflow: visible;
    transform: translateY(400%);
    position: relative;
    height: 20%;
    width: 100%;
    animation: pour-tea 2s 2s forwards;
  }

  .foam {
    display: block;
    border-radius: 30px;
    height: 40px;
    width: 40px;
    position: absolute;
  }

  .foam:nth-child(1) {
    top: 0px;
    left: -3px;
  }

  .foam:nth-child(2) {
    top: 0px;
    left: 55px;
  }

  .foam:nth-child(3) {
    width: 30px;
    height: 30px;
    border-radius: 40px;
    top: 3px;
    left: 30px;
  }

  .foam:nth-child(4) {
    width: 30px;
    height: 30px;
    border-radius: 45px;
    top: 5px;
    right: -2px;
  }

  .foam:nth-child(5) {
    top: 2px;
    right: 10px;
  }
</style>
