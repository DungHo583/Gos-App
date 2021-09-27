<template>
  <div class="label-view layout-info-product">
    <div class="label-title">
      <h3 class="title-label-view">Thông tin chung</h3>
    </div>
    <div class="label-content">
      <div class="title-label-content">
        <h3 class="title-detail-product">{{ title }}</h3>
      </div>
      <a-row :gutter="[64,0]">
        <a-col :span="12">
          <div
            class="row-info-detail"
            v-for="(left, index) in content_left"
            :key="index"
          >
            <div class="label-left">
              <p class="label-title-left">{{ left.label_title }}</p>
            </div>
            <div class="label-right">
              <p v-if="left.type == 'normal'" class="label-title-right">
                {{ left.label_content }}
                <span v-if="left.date_time">{{ left.date_time }}</span>
              </p>
              <a-tag v-if="left.type == 'tag'">{{ left.label_content }}</a-tag>
            </div>
          </div>
        </a-col>
        <a-col :span="12">
          <div
            class="row-info-detail"
            v-for="(right, index) in content_right"
            :key="index"
          >
            <div class="label-left">
              <p class="label-title-left">{{ right.label_title }}</p>
            </div>
            <div class="label-right">
              <p v-if="right.type == 'normal'" class="label-title-right">
                {{ right.label_content }}
              </p>
              <a-tag v-if="right.type == 'tag'">{{
                right.label_content
              }}</a-tag>
            </div>
          </div>
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
.layout-info-product
  padding: 20px 20px 10px 20px !important
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
  margin: 0
.label-title-right
  font-style: normal
  font-weight: normal
  font-size: 14px
  line-height: 21px
  color: #27324D
  margin: 0
.row-info-detail
  margin-bottom: 10px
  display: flex
  align-items: center
  .label-left
    width: 150px
    margin-right: 19px
  .label-right
    .ant-tag
      background-color: #dee8ff
      width: 80px
      height: 25px
      color: #4880FF
      font-style: normal
      font-weight: normal
      font-size: 14px
      display: flex
      align-items: center
      justify-content: center
      border-radius: 20px
      border-color: transparent
</style>