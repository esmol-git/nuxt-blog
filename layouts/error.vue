<template>
  <div class="error-layot">
    <div class="error-content">
      <h1 class="error-title">Ошибка 404</h1>
      <nuxt-link to="/">Вернуться на Главную</nuxt-link>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.error-layot {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.error-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 4rem;
}
.error-title {
  color: rgb(145, 6, 6);
  font-size: 60px;
  margin-bottom: 1rem;
}
</style>