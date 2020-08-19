<template>
  <div class="sensors">
    <div class="sensor" v-for="sensor in sensors" :key="sensor.name">
      <SparkLine class="sensor-chart" :data="sensor.data" />
      <div class="sensor-value">{{ sensor.data[sensor.data.length - 1] }}</div>
      <div class="sensor-name">{{ sensor.name }}</div>
    </div>
  </div>
</template>

<script>
import SparkLine from "./components/SparkLine.vue";

export default {
  name: "App",
  data() {
    return {
      sensors: [
        {
          name: "Alt Volts",
          data: [
            808,
            1475,
            1426,
            1884,
            1396,
            1280,
            1351,
            832,
            1372,
            1449,
            1425,
            999,
            1036,
            1559,
            854
          ]
        },
        { name: "Alt Amps", data: [3246, 1941, 2649, 1633, 1262] },
        { name: "Aux HP", data: [190, 128, 209, 208, 116] },
        { name: "Battery Volts", data: [73, 101, 49, 37, 62] },
        { name: "W/S Derate", data: [5, 4, 1, 2, 3] },
        { name: "Effort Kbls", data: [61, 74, 48, 52, 35] },
        { name: "Load Pot%", data: [99, 96, 95, 97, 91] },
        { name: "Max GTO °C", data: [23, 21, 44, 26, 52] },
        { name: "Prop Derate", data: [4, 2, 5, 1, 0] },
        { name: "MPH", data: [18, 20, 21, 23, 26] },
        { name: "TE", data: [8, 9, 5, 7, 6] },
        { name: "Read No.", data: [9811, 9812, 9813, 9814, 9815] },
        { name: "Engine RPM", data: [1096, 598, 661, 777, 1027] },
        { name: "Gross HP", data: [5959, 2163, 3935, 3443, 4566] },
        { name: "Water °F", data: [243, 98, 101, 193, 184] },
        { name: "Oil °F", data: [253, 143, 150, 232, 215] },
        { name: "MPH/Minute", data: [5, 6, 4, 2, 3] }
      ]
    };
  },
  components: {
    SparkLine
  }
};
</script>

<style>
body {
  background-color: #212124;
}
</style>

<style scoped>
.sensors {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  grid-gap: 20px;
  font-family: sans-serif;
  color: #d8d9da;
}

.sensor {
  max-width: 200px;
  padding: 20px;
  border-radius: 4px;
  background-color: #313133;
  text-align: center;
}

.sensor-chart {
  width: 50%;
}

.sensor-name {
  font-size: 12px;
}

.sensor-value {
  font-size: 30px;
}
</style>
