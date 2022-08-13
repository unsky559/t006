<template>
  <div class="card" tabindex="0">
    <div class="card_imageContainer">
      <img class="card_image" src="../assets/mock/1_cod%202.png" alt="" />
    </div>
    <div class="card_description">
      <div class="card_title">Омега-3 Тунец</div>
      <div class="card_description">Пептиды 1-типа из Франции</div>
      <div class="card_additional">120 капсул</div>
    </div>
  </div>
</template>

<style scoped>
.card {
  min-width: 120px;
}
.card_imageContainer {
  width: 100%;
  aspect-ratio: 1;
  background: var(--color-background-card);
  margin-bottom: 20px;
  padding: 3px;
}

.card_image {
  width: 100%;
}

.card_title {
  margin-bottom: 6px;
  font-weight: 700;
  font-size: 14px;
  line-height: 15px;
  color: var(--color-font-primary);
}
.card_description {
  margin-bottom: 6px;
  font-weight: 400;
  font-size: 12px;
  line-height: 15px;
  color: var(--color-font-primary);
}
.card_additional {
  font-weight: 500;
  font-size: 12px;
  line-height: 15px;
  color: var(--color-font-secondary);
}

@media (min-width: 720px) {
  .card{
    min-width: calc(100%/4 - 24px);
  }
}

</style>
