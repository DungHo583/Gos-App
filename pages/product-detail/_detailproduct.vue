<template>
  <div class="">
    <a-row>
      <a-col :span="17" id="info-product">
        <InfoProduct />
      </a-col>
      <a-col :span="17" id="list-product">
        <ListProduct />
      </a-col>
      <a-col :span="24">
        <VersionProduct />
      </a-col>
    </a-row>
  </div>
</template>

<script>
import InfoProduct from "./infoproduct.vue";
import ListProduct from "./listproduct.vue";
import VersionProduct from "./versionproduct.vue";

export default {
  layout: "layout-base",
  components: {
    InfoProduct,
    ListProduct,
    VersionProduct,
  },
  data() {
    return {
      title: [
        {
          title_layout: "Chi tiết sản phẩm",
          icon_layout: "arrow-left",
          btn_layout: 1,
        },
      ],
    };
  },
  created() {
    this.$parent.$emit("event", this.title);
  },
};
</script>

<style lang="sass">
#info-product
  margin-bottom: 20px

#list-product
  margin-bottom: 20px
</style>