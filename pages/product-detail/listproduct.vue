<template>
  <div class="label-view layout-list-product">
    <div class="label-title">
      <h3 class="title-label-view">Ảnh sản phẩm</h3>
    </div>
    <div class="label-content">
      <a-row :gutter="[20, 20]" type="flex">
        <a-col v-for="(item, index) in list" :key="index">
          <div class="thumbnail-view">
            <img :src="'/images/' + item.thumbnail" alt="" />
          </div>
        </a-col>
      </a-row>
    </div>
  </div>
</template>
<script>
import ItemProduct from "~/data/product.json";
export default {
  data() {
    return {
      list: ItemProduct.list_product,
    };
  },
};
</script>

<style lang="sass">
.layout-list-product
    .label-title
        margin-bottom: 25px
    .label-content
        .ant-row-flex
            .ant-col
                .thumbnail-view
                    img
                        width: 160px
                        height: 160px
                        border-radius: 10px
</style>