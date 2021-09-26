<template>
  <div class="layout-button">
    <a-button class="btn-delete">Xoá</a-button>
    <a-button class="btn-out">Thoát</a-button>
    <a-button type="primary" class="btn-edit"> Chỉnh sửa </a-button>
  </div>
</template>

<script>
export default {};
</script>

<style lang="sass">
.layout-button
    display: flex
    align-items: center
    justify-content: space-between
    .btn-delete
        border-color: #F90000
        color: #F90000
        border-radius: 5px
    .btn-out
        border-color: #27324D
        color: #27324D
        border-radius: 5px
        margin: 0 13px
    .btn-edit
        border-radius: 5px
        background: #4880FF
</style>