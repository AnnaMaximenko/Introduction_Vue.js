<template>
  <!-- <AuthComponent :isAuth="true" /> -->
  <AuthComponent :isAuth="false" />
  <hr />
  <UserList />
  <hr />
  <MortageCalculatorComponent />
</template>

<script>
import AuthComponent from "./components/AuthComponent.vue";
import MortageCalculatorComponent from "./components/MortageCalculatorComponent.vue";
import UserList from "./components/UserList.vue";
export default {
  components: {
    AuthComponent,
    UserList,
    MortageCalculatorComponent,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
