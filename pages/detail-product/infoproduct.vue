<template>
  <div class="label-view">
    <div class="label-title">
      <h3 class="title-label-view">Thông tin chung</h3>
    </div>
    <div class="label-content">
      <div class="title-label-content">
        <h3 class="title-detail-product">{{ title }}</h3>
      </div>
      <a-row :gutter="64">
        <a-col :span="12">
          <a-row v-for="(left, index) in content_left" :key="index">
            <a-col :span="12">
              <p class="label-title-left">{{ left.label_title }}</p>
            </a-col>
            <a-col :span="12">
              <p v-if="left.type == 'normal'" class="label-title-right">
                {{ left.label_content }}
              </p>
              <a-tag v-if="left.type == 'tag'">{{ left.label_content }}</a-tag>
            </a-col>
          </a-row>
        </a-col>
        <a-col :span="12">
          <a-row v-for="(right, index) in content_right" :key="index">
            <a-col :span="12">
              <p class="label-title-left">{{ right.label_title }}</p>
            </a-col>
            <a-col :span="12">
              <p v-if="right.type == 'normal'" class="label-title-right">
                {{ right.label_content }}
              </p>
              <a-tag v-if="right.type == 'tag'">{{
                right.label_content
              }}</a-tag>
            </a-col>
          </a-row>
        </a-col>
      </a-row>
    </div>
  </div>
</template>

<script>
import DataDetail from "~/data/infoproduct.json";
export default {
  data() {
    return {
      title: DataDetail.title_product,
      content_left: DataDetail.content_product_left,
      content_right: DataDetail.content_product_right,
    };
  },
};
</script>

<style lang="sass">
.label-view
    .label-title
        margin-bottom: 25px
    .label-content
        .title-label-content
            margin-bottom: 25px
            .title-detail-product
                font-style: normal
                font-weight: bold
                font-size: 17px
                line-height: 20px
                margin: 0
                color: #27324D
.label-title-left
    font-style: normal
    font-weight: normal
    font-size: 14px
    line-height: 21px
    color: #656E82
</style>