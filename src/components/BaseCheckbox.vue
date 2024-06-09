<template>
  <input
    type="checkbox"
    :checked="modelValue"
    class="field"
    @change="onChange"
  />
  <label v-if="label">{{ label }}</label>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: "",
    },
    modelValue: {
      type: Boolean,
      default: false,
    },
  },
  setup(props, { emit }) {
    const onChange = (event) => {
      emit("update:modelValue", event.target.checked);
    };

    return {
      onChange,
    };
  },
};
</script>
