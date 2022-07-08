<template>
  <div>
    <size-slider label="横" ref="width" :min="4" :max="50" :step="2" />
    <size-slider label="縦" ref="height" :min="4" :max="50" :step="2" />
    <button @click="submit">決定</button>
  </div>
</template>

<script>
import SizeSlider from "../parts/SizeSlider.vue";

export default {
  components: { SizeSlider },
  methods: {
    submit() {
      const width = this.$refs.width.value;
      const height = this.$refs.height.value;

      this.$emit("submit", width, height);
    },
  },
};
</script>

<style>
</style>