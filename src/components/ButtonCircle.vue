<template>
  <button class="circleBtn">
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
  border-radius: 50%;
}
.circleBtn:hover {
  background: var(--color-background);
}
</style>
