<script>
import IconArrowDropdown from "@/components/icons/IconArrowDropdown.vue";

export default {
  components: { IconArrowDropdown },
  props: ["title", "options"],
  data() {
    return {
      isFocused: false,
      dropdown: this.options[0],
      w: "0px",
    };
  },
  watch: {
    isFocused() {
      if (this.isFocused) {
        setTimeout(
          (w) => {
            this.$refs.select.focus();
            this.$refs.select.style.maxWidth = w;
          },
          0,
          this.w
        );
      } else {
        setTimeout(() => {
          this.w = window
            .getComputedStyle(this.$refs.button)
            .getPropertyValue("width");
        });
      }
    },
  },
  mounted() {
    this.w = window
      .getComputedStyle(this.$refs.button)
      .getPropertyValue("width");
  },
};
</script>

<template>
  <div class="dropdownContainer">
    <label>{{ title }}</label>
    <div class="holder">
      <select
        v-if="isFocused"
        v-model="dropdown"
        @blur="isFocused = false"
        ref="select"
      >
        <option v-for="(option, index) in options" :key="index">
          {{ option }}
        </option>
      </select>
      <button v-if="!isFocused" @focusin="isFocused = true" ref="button">
        <span>{{ dropdown }}</span>
        <IconArrowDropdown />
      </button>
    </div>
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
button {
  padding: 0;
  border: none;
  background: transparent;
}
span,
select {
  font-size: 16px;
  font-weight: 700;
  color: var(--color-font-primary);
  padding-right: 20px;
}
</style>
