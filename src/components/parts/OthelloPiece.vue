<template>
  <canvas :width="size" :height="size"></canvas>
</template>

<script>
export default {
  name: "OthelloPiece",
  props: {
    size: Number,
    color: Number,
  },
  watch: {
    size() {
      this.draw(this.size);
    },
  },
  computed: {
    center() {
      return this.size / 2;
    },
    radius() {
      return (this.size / 2) * 0.9;
    },
  },
  methods: {
    draw() {
      this.ctx.beginPath();
      this.ctx.clearRect(0, 0, this.size, this.size);
      this.ctx.arc(this.center, this.center, this.radius, 0, Math.PI * 2);

      if (this.color == 0) {
        this.ctx.fillStyle = "black";
      } else {
        this.ctx.fillStyle = "white";
      }
      this.ctx.fill();
    },
  },
  mounted() {
    this.ctx = this.$el.getContext("2d");
    this.draw(this.size);
  },
};
</script>

<style scoped>
canvas {
  background-color: olivedrab;
}
</style>