<template>
  <div>
    <h2>盤面の設定</h2>
    <range-slider label="横" v-model="width" :min="4" :max="50" :step="2" />
    <range-slider label="縦" v-model="height" :min="4" :max="50" :step="2" />
    <button @click="submit">決定</button>
  </div>
</template>

<script>
import RangeSlider from "../parts/RangeSlider.vue";

export default {
  components: { RangeSlider },
  data() {
    return {
      width: 4,
      height: 4,
    };
  },
  methods: {
    submit() {
      this.$emit("submit", this.width, this.height);
    },
  },
};
</script>

<style>
</style>