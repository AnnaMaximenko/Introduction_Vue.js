<template>
  <div>
    <ProductComponent
      v-for="product in products"
      :key="products.id"
      :product="product"
    />
  </div>
</template>

<script>
import ProductComponent from "./ProductComponent.vue";
export default {
  components: { ProductComponent },
  data() {
    return {
      products: [
        {
          id: 1,
          img: "https://cdn.domdivanov72.com/files/imgs/ig1111916/obedennyi-stul-sht-st37s95-1-seroe-oblakochernyi-muar-590x430.jpg",
          name: "Chair",
          price: "100",
          available: true,
        },
        {
          id: 2,
          img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRdmLfwFS8vfGZUTxxwZIVltpHFyujs6mfyCg&usqp=CAU",
          name: "Wardrobe",
          price: "99.99",
          available: false,
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
div {
  display: flex;
  gap: 5px;
}
</style>
