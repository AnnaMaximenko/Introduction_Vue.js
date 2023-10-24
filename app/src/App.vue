<template>
  <h1>Привет из арр</h1>
  <HelloComponent />
  <WorkGalary />
</template>

<script>
import HelloComponent from "./components/HelloComponent.vue";
import WorkGalary from "./components/WorkGalary.vue";
export default {
  components: { HelloComponent, WorkGalary },
};
</script>

<style lang="scss"></style>
