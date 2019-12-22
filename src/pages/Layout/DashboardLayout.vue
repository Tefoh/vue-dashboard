<template>
  <div class="wrapper">
    <!-- <div class="wrapper" :class="{'nav-open': $sidebar.showSidebar}"> -->

    <side-bar :background-color="backgroundColor">
      <!-- <mobile-menu slot="content"></mobile-menu> -->
      <sidebar-link to="/dashboard">
        <i class="tim-icons icon-chart-pie-36"></i>
        <template v-if="!isRTL">
          <p>Dashboard</p>
        </template>
        <template v-else>
          <p>داشبورد</p>
        </template>
      </sidebar-link>
      <sidebar-link to="/icons">
        <i class="tim-icons icon-atom"></i>
        <template v-if="!isRTL">
          <p>Icons</p>
        </template>
        <template v-else>
          <p>ایکون ها</p>
        </template>
      </sidebar-link>
      <sidebar-link to="/maps">
        <i class="tim-icons icon-pin"></i>
        <template v-if="!isRTL">
          <p>Maps</p>
        </template>
        <template v-else>
          <p>نقشه</p>
        </template>
      </sidebar-link>
      <sidebar-link to="/notifications">
        <i class="tim-icons icon-bell-55"></i>
        <template v-if="!isRTL">
          <p>Notifications</p>
        </template>
        <template v-else>
          <p>اطلاعیه ها</p>
        </template>
      </sidebar-link>
      <sidebar-link to="/user">
        <i class="tim-icons icon-single-02"></i>
        <template v-if="!isRTL">
          <p>User Profile</p>
        </template>
        <template v-else>
          <p>پروفایل کاربر</p>
        </template>
      </sidebar-link>
      <sidebar-link to="/table">
        <i class="tim-icons icon-puzzle-10"></i>
        <template v-if="!isRTL">
          <p>Table List</p>
        </template>
        <template v-else>
          <p>لیست جدول ها</p>
        </template>
      </sidebar-link>
      <sidebar-link to="/typography">
        <i class="tim-icons icon-align-center"></i>
        <template v-if="!isRTL">
          <p>Typography</p>
        </template>
        <template v-else>
          <p>تایپوگرافی</p>
        </template>
      </sidebar-link>
      <sidebar-link to="/dashboard?enableRTL=true">
        <i class="tim-icons icon-world"></i>
        <template v-if="!isRTL">
          <p>RTL Support</p>
        </template>
        <template v-else>
          <p>پشتیبانی RTL</p>
        </template>
      </sidebar-link>
    </side-bar>
    <sidebar-share :background-color.sync="backgroundColor"></sidebar-share>

    <div class="main-panel" :data="backgroundColor">
      <top-navbar></top-navbar>

      <dashboard-content @click.native="toggleSidebar"></dashboard-content>

      <content-footer></content-footer>
    </div>

  </div>
</template>
<style lang="scss"></style>
<script>

import TopNavbar from "./TopNavbar.vue";
import ContentFooter from "./ContentFooter.vue";
import DashboardContent from "./DashboardContent.vue";
import MobileMenu from "./MobileMenu.vue";
import SideBar from "@/components/SidebarPlugin/SideBar.vue";
import SidebarLink from "@/components/SidebarPlugin/SidebarLink.vue";



export default{
  components: {
    TopNavbar,
    DashboardContent,
    ContentFooter,
    MobileMenu,
    SideBar,
    SidebarLink
  },
  data() {
    return {
      backgroundColor: "green"
    };
  },
  computed: {
    isRTL() {
      return this.$rtl.isRTL;
    }
  },
  methods: {
    toggleSidebar() {
      if (this.$sidebar.showSidebar) {
        this.$sidebar.displaySidebar(false);
      }
    }
  }
};
</script>
