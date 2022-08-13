<script>
export default {
  props: ["tabindex"],
};
</script>

<template>
  <button class="circleBtn" :tabindex="tabindex">
    <slot />
  </button>
</template>

<style scoped>
button {
  border: none;
  background: none;
}
.circleBtn {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 11px;
}
.circleBtn:hover {
  cursor: pointer;
}

@media (min-width: 720px) {
  .circleBtn {
    padding: 5px;
  }
}
</style>
