<template>
  <div class="label-view layout-version-product">
    <div class="label-title">
      <h3 class="title-label-view">Các phiên bản (4)</h3>
    </div>
    <div class="label-content">
      <table class="table-data-version">
        <thead class="title-table-data">
          <th style="text-align: center">#</th>
          <th>Tên phiên bản</th>
          <th>Hình ảnh</th>
          <th>Mã sản phẩm</th>
          <th>Mã vạch</th>
          <th>Giá vốn</th>
          <th>Giá bán lẻ</th>
          <th>Giá bán buôn</th>
          <th>Khối lượng</th>
          <th>Tổng đã nhập</th>
          <th>Tồn kho</th>
          <th>Có thể bán</th>
          <th>Lịch sử kho</th>
        </thead>
        <tbody>
          <tr v-for="(item, index) in product" :key="index">
            <td style="text-align: center">{{ index + 1 }}</td>
            <td class="name-version-product">{{ item.name_product }}</td>
            <td>
              <div class="avt-product">
                <img
                  class="product-img"
                  v-if="item.avt_product != ''"
                  :src="'/images/' + item.avt_product"
                  alt=""
                />
                <img
                  class="nosignal-img"
                  v-if="item.avt_product == ''"
                  src="/images/no-img.svg"
                  alt=""
                />
              </div>
            </td>
            <td>{{ item.code }}</td>
            <td>{{ item.barcode }}</td>
            <td>{{ item.cost_price }}</td>
            <td style="text-align: right">{{ item.retail_price }}</td>
            <td style="text-align: right">{{ item.wholesale_price }}</td>
            <td style="text-align: right">{{ item.weigh }}</td>
            <td style="text-align: right">{{ item.product_input }}</td>
            <td style="text-align: right">{{ item.inventory }} <span class="icon-seemore"><a-icon type="eye" /></span></td>
            <td style="text-align: right">{{ item.can_sell }} <span class="icon-seemore"><a-icon type="eye" /></span></td>
            <td class="history-warehouse">
              <a href="javascript:;">Bấm để xem</a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import ProductList from "~/data/product.json";
export default {
  data() {
    return {
      product: ProductList.list_product,
    };
  },
};
</script>

<style lang="sass">
.layout-version-product
  overflow: hidden
  .label-title
    margin-bottom: 20px
  .label-content
    margin: 0 -20px !important 
    overflow-x: scroll
    .table-data-version
      width: max-content
      .title-table-data
        th
          font-style: normal
          font-weight: normal
          font-size: 14px
          line-height: 21px
          color: #656E82
          padding: 10px 20px
      tbody
        tr
          td
            color: #27324D
            font-style: normal
            font-weight: normal
            font-size: 14px
            line-height: 21px
            padding: 10px 20px
            .icon-seemore 
              margin-left: 10px 
              cursor: pointer
              .anticon
                color: #4880FF
          .name-version-product
            word-break: break-word
            width: 240px
          .history-warehouse
            text-decoration-line: underline
            color: #4880FF
        tr:hover 
          background: #F5F6FA
.avt-product
  background: #EAEBF0
  border-radius: 5px
  display: flex
  align-items: center
  justify-content: center
  width: max-content
  .nosignal-img
    margin: 7px 4px
  .product-img
    width: 35px
    height: 35px
</style>