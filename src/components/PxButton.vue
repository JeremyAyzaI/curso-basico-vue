<template>
  <button
    @click="buttonClick"
    class="bg-transparent hover:bg-green-500 text-green-700 font-semibold hover:text-white p-2"
  >
    <beat-loader :loading="isLoading" :color="'#68d391'" :size="8"></beat-loader>
    <p v-show="!isLoading">
      <slot></slot>
    </p>
  </button>
</template>

<script>
export default {
  name: "PxButton",

  data() {
    return {};
  },
  props: {
    isLoading: {
      type: Boolean,
      default: false,
    },
  },
  mounted() {},

  methods: {
    buttonClick() {
      this.$emit("custom-click");
    },
  },
};
</script>
