<template>
  <a-layout id="layout-base">
    <a-layout-sider
      v-model="collapsed"
      :trigger="null"
      collapsible
      :width="240"
      :class="['layout-sidebar', collapsed ? 'side-close' : '']"
    >
      <div
        class="logo"
        :style="
          collapsed ? 'margin: 23px 10px' : 'margin: 23px 16px'
        "
      >
        <a href="/">
          <img
            :style="
              collapsed
                ? 'width: 40px; height: 40px;'
                : ''
            "
            :src="
              collapsed ? '/images/logo_sidebar.svg' : '/images/logopage.png'
            "
            alt=""
          />
        </a>
      </div>
      <a-button
        type="primary"
        class="btn-open-sidebar"
        @click="toggleCollapsed"
      >
        <a-icon :type="collapsed ? 'right' : 'left'" />
      </a-button>
      <a-menu mode="inline" class="menu">
        <template v-for="(item, index) in category">
          <a-menu-item v-if="item.child == null" :key="index">
            <a-icon :type="item.icon" />
            <span>{{ item.title }}</span>
          </a-menu-item>
          <a-sub-menu v-if="item.child != null" :key="index">
            <span slot="title">
              <a-icon :type="item.icon" />
              <span>{{ item.title }}</span>
            </span>
            <a-menu-item v-for="(item, index) in item.child" :key="index">
              {{ item.title }}
            </a-menu-item>
          </a-sub-menu>
        </template>
      </a-menu>
    </a-layout-sider>
    <a-layout>
      <a-layout-header style="background: #fff; padding: 0">
        <div class="content-topbar">
          <div class="content-topbar-left">
            <a-icon
              class="trigger"
              :type="collapsed ? 'menu' : 'menu'"
              @click="() => (collapsed = !collapsed)"
            />
            <h3>Dashboard</h3>
          </div>
          <div class="content-topbar-right">
            <div class="logo-name"><span>SC</span></div>
            <p>Sun Cosmetic</p>
            <div class="avt-user">
              <img src="/images/user.svg" alt="" />
            </div>
            <div class="language">
              <img src="/images/languege_vn.svg" alt="" />
              <p>VN</p>
            </div>
          </div>
        </div>
      </a-layout-header>
      <a-layout-content>
        <Nuxt />
      </a-layout-content>
    </a-layout>
  </a-layout>
</template>
<script>
import CategoryData from "~/data/category.json";
export default {
  data() {
    return {
      collapsed: true,
      category: CategoryData.list_menu,
    };
  },
  methods: {
    toggleCollapsed() {
      this.collapsed = !this.collapsed;
    },
  },
};
</script>
<style lang="sass">
.side-close
  width: 69px !important
  min-width: 69px !important
  max-width: 69px !important
  flex: 0 0 69px !important

.layout-sidebar
  position: relative
  .btn-open-sidebar
    position: absolute
    right: -11px
    top: 135px
    padding: 0 !important
    width: 22px
    height: 22px
    background-color: #fff !important
    display: flex
    align-items: center
    justify-content: center
    border-color: #fff
    border-radius: 50%
    .anticon
      color: #000
      font-size: 9px
  .ant-menu
    background: #1e2f56
    padding: 0 13px
    .ant-menu-item
      padding: 13px !important
      display: flex
      align-items: center
      border-radius: 10px
      .anticon
        color: #fff
      span
        color: #fff
    .ant-menu-item:active
      background-color: #4880FF !important
    .ant-menu-item-active
      color: #fff
      background-color: #4880FF
    .ant-menu-item-selected
      color: #fff
      background-color: #4880FF
    .ant-menu-submenu
      border-radius: 10px
      .ant-menu-submenu-title
        padding: 13px !important
        display: flex
        align-items: center
        .ant-menu-submenu-arrow
          width: 16px
          height: 16px
          border-radius: 50%
          background-color: #404e6f
          display: flex
          align-items: center
          justify-content: center
          top: auto
        span
          line-height: 0
          .anticon
            color: #fff
          span
            color: #fff

      .ant-menu-sub
        .ant-menu-item
          color: #fff
      .ant-menu-submenu-title:active
        color: #fff
        background-color: #4880FF
      .ant-menu-submenu-title:hover
        color: #fff
        .ant-menu-submenu-arrow::before
          background: #fff !important
        .ant-menu-submenu-arrow::after
          background: #fff !important
    .ant-menu-submenu-active
      color: #fff
      background-color: #4880FF
.ant-menu-submenu-inline
  .ant-menu
    background-color: #1e2f56 !important
    margin-left: 0px !important
    padding: 0px 12px !important
    border-radius: 0px !important
  .ant-menu-submenu-arrow::before
    background-image: linear-gradient(to right, rgb(255 255 255), rgb(255 255 255)) !important
    margin-top: 3px
    margin-bottom: 0
  .ant-menu-submenu-arrow::after
    background-image: linear-gradient(to right, rgb(255 255 255), rgb(255 255 255)) !important
    margin-top: 3px
    margin-bottom: 0

.ant-menu-submenu-open
  .ant-menu-submenu-arrow::before
    margin-bottom: 3px
    margin-top: 0
  .ant-menu-submenu-arrow::after
    margin-bottom: 3px
    margin-top: 0

.ant-menu-inline-collapsed
  .ant-menu-submenu
    .ant-menu-submenu-arrow
      display: none !important
  .anticon
    line-height: 0 !important

.ant-menu-submenu
  border-radius: 10px
  .ant-menu
    background-color: #1e2f56 !important
    margin-left: 12px
    padding: 5px 12px
    border-radius: 10px

.ant-menu-item
  color: #fff
  border-radius: 10px

.ant-menu-item-active
  color: #fff !important

.ant-menu-item:active
  background: #4880FF

.ant-menu-item:hover
  background: #4880FF
  .ant-menu-item-active
    color: #fff
</style>