<template>
  <div>
    <bounce-loader :loading="isLoading" :color="'#68d391'" :size="100" />
    <px-assets-table v-if="!isLoading" :assets="assets"></px-assets-table>
  </div>
</template>

<script>
import api from "@/api";
import PxAssetsTable from "@/components/PxAssetsTable.vue";
export default {
  components: { PxAssetsTable },
  name: "HomeComponent",

  data() {
    return {
      assets: [],
      isLoading: false,
    };
  },
  methods: {},
  created() {
    this.isLoading = true;

    api
      .getAssets()
      .then((data) => (this.assets = data))
      .finally(() => (this.isLoading = false));
  },
};
</script>
