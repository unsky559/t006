<script lang="js">
import ButtonCircle from "@/components/ButtonCircle.vue";
import IconClose from "@/components/icons/IconClose.vue";
import Dropdown from "@/components/Dropdown.vue";
import SideBarLinks from "@/components/SideBar/SideBarLinks.vue";


export default {
  components: { ButtonCircle, IconClose, Dropdown, SideBarLinks },
  props: ["close"],
  emits: ["menuClose"],
  mounted() {
    document.addEventListener("keydown", (e) => {
      if (e.keyCode === 27) {
        this.$emit('menuClose');
      }
    });
  },
};
</script>

<template>
  <transition name="side">
    <div v-if="!close" class="sideBar">
      <div class="sideBar_header">
        <ButtonCircle @click="$emit('menuClose')" tabindex="1">
          <IconClose />
        </ButtonCircle>
      </div>

      <div class="sideBar_screen">
        <SideBarLinks />
      </div>

      <div class="sideBar_footer">
        <div class="sideBar_settings">
          <Dropdown></Dropdown>
          <Dropdown></Dropdown>
          <Dropdown></Dropdown>
        </div>
      </div>
    </div>
  </transition>
  <transition name="side">
    <div v-if="!close" class="background" @click="$emit('menuClose')"></div>
  </transition>
</template>

<style scoped>
.side-enter-to,
.side-leave-from {
  transform: translateX(0%);
}
.side-enter-active,
.side-leave-active {
  transition: transform 0.8s var(--cubic-function);
}

 .side-enter-from,
.side-leave-to {
  transform: translateX(-100%);
}


.background{
  position: fixed;
  width: 100%;
  height: 100%;
  background: var(--color-background-trans);
  z-index: 1;
}

.sideBar {
  max-width: 432px;
  position: fixed;
  width: 100vw;
  height: 100vh;
  background: var(--color-background-light);
  z-index: 2;

  display: flex;
  flex-direction: column;
  overflow-y: auto;
}
.sideBar_header {
  padding: 0 25px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding-top: 26px;
  padding-bottom: 19px;
}

.sideBar_screen {
  display: flex;
  flex-grow: 1;
  overflow-y: auto;
  min-height: 200px;
  flex-wrap: wrap;
  flex-direction: column;
  overflow-x: hidden;
}

.sideBar_footer {
  padding: 0 34px;
}

.sideBar_settings {
  padding-top: 45px;
  padding-bottom: 55px;
  display: flex;
  justify-content: space-between;
}

.sideBar_settings {
  border-top: 1px solid var(--color-font-secondary);
}
</style>
