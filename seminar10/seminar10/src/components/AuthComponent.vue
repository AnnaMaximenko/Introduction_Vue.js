<!-- Создайте компонент "Аутентификация" (Authentication), который будет отображать форму входа или сообщение об успешной аутентификации в зависимости от переданного пропса isAuthenticated. Используйте директиву v-if для условного отображения разных элементов в шаблоне компонента. -->

<template>
  <div v-if="isAuth">
    <h2>Успешная регистрация</h2>
  </div>
  <div v-else>
    <h2>Необходимо зарегистрироваться</h2>
    <form>
      <label>Name <input type="text" /></label>
      <label>Email <input type="email" /></label>
      <label>Password <input type="password" /></label>
      <button>Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    isAuth: Boolean,
  },
};
</script>

<style lang="scss" scoped></style>
