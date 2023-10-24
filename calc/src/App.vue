<template>
  <div>Мой новый калькулятор</div>
  <div id="app">
    <CalcFunction />
  </div>
</template>

<script>
import CalcFunction from "./components/CalcFunction.vue";
export default {
  name: "App",
  components: {
    CalcFunction,
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
