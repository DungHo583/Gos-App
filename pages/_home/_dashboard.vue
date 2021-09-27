<template>
  <div class="">
    <a-row :gutter="20">
      <a-col :span="16">
        <FilterData />
      </a-col>
      <a-col :span="8"> Test2 </a-col>
    </a-row>
  </div>
</template>

<script>
import FilterData from "./layout-filter.vue";
export default {
  layout: "layout-base",
  components: {
    FilterData,
  },
};
</script>

<style lang="sass">
</style>