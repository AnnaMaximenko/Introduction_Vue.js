<template>
  <div>
    <img :src="product.img" alt="" />
    <h2>{{ product.name }}</h2>
    <h2>{{ formattedPrice }}</h2>
    <h3 v-if="product.available">Available</h3>
    <h3 v-else>Out of stock</h3>
  </div>
</template>

<script>
export default {
  props: { product: Object },
  computed: {
    formattedPrice() {
      return `$${this.product.price}`;
    },
  },
};
</script>

<style lang="scss" scoped>
div {
  width: 500px;
  height: 500px;
  border: 1px solid #000;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  border-radius: 10%;
  cursor: pointer;
}
div:hover {
  border: 1px solid #9c7878;
}
img {
  width: 200px;
  height: 200px;
}
</style>
