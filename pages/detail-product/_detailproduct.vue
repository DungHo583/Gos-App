<template>
  <div class="">
    <a-row>
      <a-col :span="16">
          <InfoProduct />
      </a-col>
      <a-col :span="16"> col-4 </a-col>
    </a-row>
  </div>
</template>

<script>
import InfoProduct from "./infoproduct.vue"
export default {
  layout: "layout-base",
    components: {
        InfoProduct,
    }
};
</script>

<style lang="sass">
</style>