<script lang="js">
import IconCall from "@/components/icons/IconCall.vue";
import IconArrowForward from "@/components/icons/IconArrowForward.vue";
import IconArrowBack from "@/components/icons/IconArrowBack.vue";

export default {
  data() {
    return {
      pages: [
        {
          links: [
            {
              text: "Все продукты",
              links: [
                {
                  text: "Продукты для взрослых",
                  categoryLinks: [
                    { text: "Все" },
                    { text: "Коллаген" },
                    { text: "Омега-3 Тунец" },
                    { text: "Омега-3 Треска" },
                    { text: "Витамин Д3   2000 МЕ" },
                    { text: "Витамин Д3   5000 МЕ" },
                    { text: "Витамин Д3 + K2" },
                    { text: "Сквален" },
                    { text: "Акулий жир" },
                  ],
                },
                {
                  text: "Продукты для детей",
                  categoryLinks: [
                    { text: "Все" },
                    { text: "Kids Омега-3  Тунец" },
                    { text: "Kids Омега-3  Треска" },
                    { text: "Kids Витамин Д3" },
                  ],
                },
              ],
            },
            { text: "О компании" },
            { text: "Сертификаты" },
            { text: "Вопрос-ответ" },
            { text: "Блог" },
          ],
        },
      ],
    };
  },
  mounted() {
    this.$refs.back.focus();
  },
  components: { IconArrowBack, IconArrowForward, IconCall },
};
</script>
<template>
  <transition-group name="test">
    <div
      class="sideBar_links"
      v-for="(page, pageIndex) in pages"
      :key="pageIndex"
      :style="{ transform: `translateX(${-100 * (pages.length - 1)}%)` }"
      ref="back"
    >
      <div v-if="page.links" style="height: 100%">
        <button class="linkBack" v-if="pageIndex > 0" @click="pages.pop()">
          <span class="linkBack_icon">
            <IconArrowBack />
          </span>

          {{ page.text }}
        </button>

        <ul class="linklist mainlist">
          <li
            v-for="(link, index) in page.links"
            :key="index"
            :class="{
              linklist_link: !pageIndex,
              linklist_link__light: pageIndex,
            }"
          >
            <a href="#">
              {{ link.text }}
            </a>

            <ul v-if="link.links" class="linklist_sub">
              <li
                v-for="(subLink, subLinkIndex) in link.links"
                :key="subLinkIndex"
                @click="
                  pages.push({
                    links: subLink.categoryLinks,
                    text: subLink.text,
                  })
                "
              >
                <a href="#">
                  {{ subLink.text }}
                  <span class="linklist_sub__icon">
                    <IconArrowForward />
                  </span>
                </a>

              </li>
            </ul>
          </li>
        </ul>
      </div>

      <template v-if="pageIndex === 0">
        <ul class="linklist">
          <li class="linklist_link"><a href="#">Доставка и оплата</a></li>
          <li class="linklist_link"><a href="#">Контакты</a></li>
          <li class="linklist_link"><a href="#">Вакансии</a></li>
        </ul>

        <div class="sideBar_contact">
          <p class="sideBar_number">
            <span class="sideBar_number__icon">
              <IconCall />
            </span>
            0 800 330 039
          </p>
          <p class="sideBar_contact__secondary">
            Call-центр работает<br /><strong>с 7:00 до 23:00</strong>
          </p>
        </div>
      </template>
    </div>
  </transition-group>
</template>
<style scoped>
.test-enter-to,
.test-leave-from {
  left: 0%;
}
.test-enter-from,
.test-leave-to {
  left: 100%;
}

.sideBar_links {
  position: relative;
  width: 100%;
  height: 100%;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  transition: transform 0.8s var(--cubic-function),
    left 0.8s var(--cubic-function);
}

.sideBar_links {
  padding: 0 34px;
}

.linklist {
  padding: 4px 0;
}
.mainlist {
  flex-grow: 1;
  padding-bottom: 40px;
}

.linkBack {
  display: flex;
  align-items: center;
  margin-bottom: 25px;
  font-size: 16px;
  font-weight: 700;

  color: var(--color-font-primary);

  background: transparent;
  border: none;

  padding: 6px 0;
}
.linkBack:hover{
  cursor: pointer;
}
.linkBack_icon {
  margin-right: 25px;
}

.linklist > li {
  list-style: none;
}
.linklist > li:not(:last-child) {
  margin-bottom: 18px;
}

.linklist_sub > li {
  list-style: none;
  display: flex;
  align-items: center;
}
.linklist_sub > li:not(:last-child) {
  margin-bottom: 19px;
}

.linklist_link {
  font-size: 16px;
  font-weight: 700;
  color: var(--color-font-primary);
}
.linklist_link__light {
  font-size: 16px;
  font-weight: 500;
  color: var(--color-font-primary);
}

.linklist_sub {
  padding: 28px 0 6px 0;
}
.linklist_sub {
  font-size: 16px;
  font-weight: 500;
  color: var(--color-font-primary);
}

.linklist_sub__icon {
  margin-left: 28px;
  display: flex;
  align-items: center;
}
.sideBar_contact {
  padding-top: 34px;
  padding-bottom: 42px;
  display: flex;
  justify-content: space-between;
}
.sideBar_contact__secondary {
  font-size: 12px;
  font-weight: 400;
  color: var(--color-font-secondary);
}
.sideBar_contact__secondary strong {
  font-weight: 700;
}
.sideBar_number {
  font-size: 22px;
  font-weight: 700;
  color: var(--color-font-primary);
}

.sideBar_number__icon {
  padding: 10px;
}
</style>
