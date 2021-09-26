<template>
  <div class="label-view layout-version-product">
    <div class="label-title">
      <h3 class="title-label-view">Các phiên bản (4)</h3>
    </div>
    <div class="label-content">
      <table>
        <thead>
          <th>#</th>
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
            <td>{{ index+1 }}</td>
            <td>{{ item.name_product }}</td>
            <td>{{ item.avt_product }}</td>
            <td>{{ item.code }}</td>
            <td>{{ item.barcode }}</td>
            <td>{{ item.cost_price }}</td>
            <td>{{ item.retail_price }}</td>
            <td>{{ item.wholesale_price }}</td>
            <td>{{ item.weigh }}</td>
            <td>{{ item.product }}</td>
            <td>{{ item.inventory }}</td>
            <td>{{ item.can_sell }}</td>
            <td>
                <a href="javascript:;">Bấm để xem</a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import ProductList from "~/data/product.json"
export default {
    data() {
        return {
            product: ProductList.list_product
        }
    }
};
</script>

<style lang="sass">
.layout-version-product 
    .label-title
        margin-bottom: 20px
</style>