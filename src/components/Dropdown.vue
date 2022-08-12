<script lang="ts">
import IconArrowDropdown from "@/components/icons/IconArrowDropdown.vue";

export default {
  components: { IconArrowDropdown },
};
</script>

<template>
  <div class="dropdownContainer">
    <label>Доставка</label>
    <span>Украина</span>
    <IconArrowDropdown />
  </div>
</template>

<style scoped>
label {
  display: block;
  font-size: 12px;
  font-weight: 500;
  color: var(--color-font-secondary);
  margin-bottom: 4px;
}
span {
  font-size: 16px;
  font-weight: 700;
  color: var(--color-font-primary);
  padding-right: 20px;
}
</style>
