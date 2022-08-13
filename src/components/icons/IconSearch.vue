<template>
  <svg
    width="20"
    height="20"
    viewBox="0 0 20 20"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <circle
      class="cirle"
      cx="7.52021"
      cy="8.01313"
      r="6.52021"
      stroke="#00284F"
      stroke-width="2"
    />
    <path
      class="hoverable"
      d="M17.8001 19.7071C18.1906 20.0977 18.8238 20.0976 19.2143 19.7071C19.6048 19.3166 19.6048 18.6834 19.2143 18.2929L17.8001 19.7071ZM11.3711 13.2782L17.8001 19.7071L19.2143 18.2929L12.7854 11.864L11.3711 13.2782Z"
      fill="#00284F"
    />
  </svg>
</template>
<style scoped>
button:hover .cirle {
  stroke: var(--color-accent);
}

button:hover .hoverable {
  fill: var(--color-accent);
}

svg * {
  transition: 0.3s;
}

@media (min-width: 720px) {
  svg {
    width: 26px;
    height: 26px;
  }
}
</style>
