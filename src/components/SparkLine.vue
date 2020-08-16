<template>
  <svg :id="id" viewBox="0 0 200 40">
    <path d="M 0 20 H 200" fill="none" stroke-width="3" stroke="gold" />
  </svg>
</template>

<script>
import * as d3 from "d3";
import { nanoid } from "nanoid";

export default {
  name: "SparkLine",
  props: {
    data: {
      type: Array,
      default() {
        return [0, 0];
      }
    }
  },
  data() {
    return {
      id: `chart-${nanoid()}`
    };
  },
  watch: {
    data() {
      this.plot();
    }
  },
  methods: {
    plot() {
      this.x.domain([0, this.data.length - 1]);
      this.y.domain(d3.extent(this.data));
      this.chart.select("path").attr("d", this.line(this.data));
    }
  },
  mounted() {
    this.chart = d3.select(`#${this.id}`);

    this.x = d3.scaleLinear().range([0, 200]);

    this.y = d3.scaleLinear().range([40, 0]);

    this.line = d3
      .line()
      .x((d, i) => this.x(i))
      .y(d => this.y(d));

    this.plot();
  }
};
</script>
