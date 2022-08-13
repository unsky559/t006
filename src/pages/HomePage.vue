<script lang="ts">
import Card from "@/components/Card.vue";

export default {
  components: { Card },
};
</script>

<template>
  <div class="row">
    <div class="container">

      <aside class="section asideLinks">
        <h2 class="textSecondary">Популярное в этой категории</h2>
        <ul class="linklist">
          <li class="linklist_link"><a href="#">Коллаген</a></li>
          <li class="linklist_link"><a href="#">Омега-3</a></li>
          <li class="linklist_link"><a href="#">Витамин Д3</a></li>
          <li class="linklist_link"><a href="#">Сквален</a></li>
          <li class="linklist_link"><a href="#">Витамины для детей</a></li>
        </ul>
      </aside>

      <section class="section popular">
        <h2 class="textSecondary">Популярное в этой категории</h2>
        <div class="cardList">
          <Card />
          <Card />
          <Card />
          <Card />
        </div>
      </section>

    </div>
  </div>

  <div class="container">

  </div>
</template>
<style scoped>

h2 {
  margin-bottom: 28px;
}

.row{
  background: var(--color-background-section);
}

.section{
  padding-top: 62px;
  padding-bottom: 50px;
}

.linklist{
  padding: 0;
}

.linklist_link {
  font-size: 16px;
  font-weight: 500;
  color: var(--color-font-primary);
}

.linklist > li {
  list-style: none;
}
.linklist > li:not(:last-child) {
  margin-bottom: 18px;
}

.container {
  padding: 0 36px;
}

.row > .container{
  display: flex;
}

.asideLinks{
  width: calc(100% / 12 * 3);
}
.popular{
  width: calc(100% / 12 * 9);
}
@media (max-width: 1000px) {
  .asideLinks{
    display: none;
  }
  .popular{
    width: 100%;
  }
}

.cardList {
  display: flex;
  flex-wrap: nowrap;
  overflow-x: auto;
}
.cardList > *:not(:last-child) {
  margin-right: 24px;
}


@media (min-width: 1450px) {
  .cardList{
    flex-wrap: wrap;
  }
}

</style>
