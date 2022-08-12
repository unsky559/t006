<script lang="js">
import HeaderComponent from "@/components/HeaderComponent.vue";
import HomePage from "@/pages/HomePage.vue";
import SideBar from "@/components/SideBar/SideBar.vue";
export default {
  components: { SideBar, HeaderComponent, HomePage },
  data() {
    return {
      sideBarClosed: true
    }
  },
}
</script>

<template>
  <SideBar
    :close="sideBarClosed"
    @menuClose="
      () => {
        this.sideBarClosed = true;
      }
    "
  />
  <HeaderComponent
    @menuClick="
      () => {
        this.sideBarClosed = false;
      }
    "
  />
  <HomePage />
</template>

<style scoped></style>
