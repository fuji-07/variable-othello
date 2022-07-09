<template>
  <div>
    {{ label }}:{{ modelValue }}<br />
    <input
      type="range"
      :value="modelValue"
      :min="min"
      :max="max"
      :step="step"
      @input="$emit('update:modelValue', Number($event.target.value))"
    />
  </div>
</template>

<script>
export default {
  name: "SizeSlider",
  props: {
    label: String,
    min: Number,
    max: Number,
    step: Number,
    modelValue: Number,
  },
};
</script>