<template>
  <div style="width:100px">
    <SparkLine :data="[808, 1475, 1426, 1884, 1396]" />
    <SparkLine :data="[3246, 1941, 2649, 1633, 1262]" />
    <SparkLine :data="[190, 128, 209, 208, 116]" />
  </div>
</template>

<script>
import SparkLine from "./components/SparkLine.vue";

export default {
  name: "App",
  components: {
    SparkLine
  }
};
</script>
