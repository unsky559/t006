<script lang="ts">
import ButtonCircle from "@/components/ButtonCircle.vue";
import IconMenu from "@/components/icons/IconMenu.vue";
import IconSearch from "@/components/icons/IconSearch.vue";
import IconUser from "@/components/icons/IconUser.vue";
import UserCart from "@/components/icons/IconCart.vue";
import LogoComponent from "@/components/LogoComponent.vue";

export default {
  components: {
    ButtonCircle,
    IconMenu,
    IconSearch,
    IconUser,
    UserCart,
    LogoComponent,
  },
  emits: ["menuClick"],
};
</script>
<template>
  <header class="header">
    <div class="container">
      <div class="header_controls">
        <div class="controls_combine">
          <ButtonCircle @click="$emit('menuClick')">
            <IconMenu />
          </ButtonCircle>
          <ButtonCircle>
            <IconSearch />
          </ButtonCircle>
        </div>
        <LogoComponent />
        <div class="controls_combine">
          <ButtonCircle>
            <IconUser />
          </ButtonCircle>
          <ButtonCircle>
            <UserCart />
          </ButtonCircle>
        </div>
      </div>
      <div class="header_links">
        <ul class="links">
          <li class="links_li links_li__active"><a href="#">Омега-3</a></li>
          <li class="links_li"><a href="#">Витамины</a></li>
          <li class="links_li"><a href="#">Добавки</a></li>
          <li class="links_li mobile_hide"><a href="#">Доставка</a></li>
          <li class="links_li"><a href="#">О нас</a></li>
        </ul>
      </div>
    </div>

    <div class="header_links"></div>
  </header>
</template>

<style scoped>
.header {
  background: var(--color-background-light);
}
.header_controls {
  padding-top: 50px;
  padding-bottom: 13px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.controls_combine {
  display: flex;
}

.links {
  padding: 0;
  display: flex;
  padding: 12px;
  overflow-x: auto;
  flex-wrap: nowrap;
}
.links_li {
  white-space: nowrap;
  list-style: none;
  margin-right: 30px;
  font-size: 16px;
  color: var(--color-font-primary);
}
.links_li:last-child {
  margin-right: 0;
}
.links_li__active {
  font-weight: bold;
}

@media (min-width: 720px) {
  .links {
    justify-content: center;
  }
  .links_li {
    margin-right: 52px;
  }
  .header_controls {
    padding-top: 26px;
    padding-bottom: 26px;
  }
  .links {
    padding-bottom: 24px;
  }
  .controls_combine > *:not(:last-child) {
    margin-right: 25px;
  }
}
</style>
