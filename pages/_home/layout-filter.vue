<template>
  <div class="layout-filter-data">
    <div class="layout-filer-content-left">
      <div class="title-filter-data">
        <h4 class="title-filter">So sánh thống kê:</h4>
      </div>
      <div class="input-select-data">
        <a-select default-value="1" style="width: 133px" @change="handleChange">
          <a-select-option value="1"> 30 ngày qua </a-select-option>
          <a-select-option value="2"> 15 ngày qua </a-select-option>
          <a-select-option value="3"> 7 ngày qua </a-select-option>
          <a-select-option value="4"> 3 ngày qua </a-select-option>
        </a-select>
      </div>
      <span class="word-connect-layout">
        <h4 class="word-connect">với</h4>
      </span>
      <div class="input-select-data">
        <a-select
          default-value="1"
          style="width: 150px"
          @change="handleChange2"
        >
          <a-select-option value="1"> 30 ngày trước đó </a-select-option>
          <a-select-option value="2"> 15 ngày trước đó </a-select-option>
          <a-select-option value="3"> 7 ngày trước đó </a-select-option>
          <a-select-option value="4"> 3 ngày trước đó </a-select-option>
        </a-select>
      </div>
    </div>
    <div class="layout-filer-content-right">
      <div class="title-filter-warehouse">
        <h4 class="title-filter">Chọn kho:</h4>
      </div>
      <div class="input-select-warehouse">
        <a-select
          default-value="1"
          style="width: 153px"
          @change="handleChange3"
        >
          <a-select-option value="1"> Tất cả các kho </a-select-option>
          <a-select-option value="2"> ... </a-select-option>
          <a-select-option value="3"> ... </a-select-option>
          <a-select-option value="4"> ... </a-select-option>
        </a-select>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="sass">
.layout-filter-data
    display: flex
    align-items: center
    justify-content: space-between
    .layout-filer-content-left
        display: flex
        align-items: center
        .title-filter-data
            margin-right: 10px
            .title-filter
                font-style: normal
                font-weight: normal
                font-size: 14px
                line-height: 21px
                color: #656E82
                margin: 0
        .word-connect-layout
            margin: 0 10px
            .word-connect
                margin: 0
                font-style: normal
                font-weight: normal
                font-size: 14px
                line-height: 21px
                color: #656E82
    .layout-filer-content-right
        display: flex
        align-items: center
        .title-filter-warehouse
            margin-right: 10px
            .title-filter
                font-style: normal
                font-weight: normal
                font-size: 14px
                line-height: 21px
                color: #656E82
                margin: 0
.input-select-data
    .ant-select
        border: 1px solid #DCDFE5
        box-sizing: border-box
        border-radius: 5px
        ont-style: normal
        font-weight: normal
        font-size: 14px
        line-height: 21px
        color: #27324D
</style>