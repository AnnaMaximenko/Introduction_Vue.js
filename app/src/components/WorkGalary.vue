<!-- Создайте компонент галереи изображений, который будет отображать одно большое изображения и под ним будет находиться три мини изображения, при клике на любое мини изображение оно будет отображаться вместо большого изображения. -->
<template>
  <div>
    <img class="big" :src="bigImg" width="600" height="400" />
    <div>
      <img
        @click="changeImg(cat)"
        v-for="(cat, index) in cats"
        :key="index"
        :src="cat"
        width="150"
        height="100"
      />
    </div>
  </div>
</template>

<script>
import img1 from "@/assets/img/1.jpg";
import img2 from "@/assets/img/2.jpg";

export default {
  data() {
    return {
      cats: {
        cat1: img1,
        cat2: img2,
        cat3: require("@/assets/img/3.jpg"),
        cat4: require("@/assets/img/5.jpeg"),
      },
      bigImg: "",
    };
  },
  methods: {
    changeImg(url) {
      this.bigImg = url;
    },
  },
};
</script>

<style lang="scss" scoped></style>
