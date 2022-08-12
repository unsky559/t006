<script lang="ts">
import Card from "@/components/Card.vue";

export default {
  components: { Card },
};
</script>

<template>
  <section>
    <div class="cardList">
      <Card />
      <Card />
      <Card />
      <Card />
    </div>
  </section>
  <div class="container">
    <h2 class="textSecondary">Популярное в этой категории</h2>
  </div>
</template>
<style scoped>
.container {
  padding: 0 36px;
}

h2 {
  margin-top: 36px;
  margin-bottom: 36px;
}

section {
  background: var(--color-background-section);
}

.cardList {
  padding: 45px 36px;
  display: flex;
  flex-wrap: nowrap;
  overflow-x: auto;
}
.cardList > *:not(:last-child) {
  margin-right: 24px;
}
</style>
