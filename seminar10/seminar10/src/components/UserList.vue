<!-- Создать компонент UserList, который будет отображать список пользователей из переданного массива. Каждый пользователь должен быть представлен в виде отдельного компонента User, принимающего пропсы с данными о пользователе (например, имя, фамилия, эл. почта) -->

<template>
  <div>
    <UserComponent v-for="person in users" :key="person.id" :user="person" />
  </div>
</template>

<script>
import UserComponent from "./UserComponent.vue";

export default {
  components: { UserComponent },
  data() {
    return {
      users: [
        {
          id: 1,
          name: "Bob",
          surname: "Marley",
          email: "bobmarley@bob.com",
        },
        {
          id: 2,
          name: "Walt",
          surname: "Disney",
          email: "disney@wb.com",
        },
        {
          id: 3,
          name: "Tom",
          surname: "Cruse",
          email: "tom@cruse.com",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
div {
  display: flex;
  gap: 20px;
}
</style>
