<template>
  <div class="container bg-slate-50 mx-auto mt-10 p-5">
    <h1 class="mb-5">Users List ( {{ users.length }} )</h1>
    <core-is-loading v-if="isLoading" />
    <users-list :users="users" />
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from "vue";
import type { User } from "./interfaces/user";
import CoreIsLoading from "./components/Core/CoreIsLoading.vue";
import UsersList from "./components/Users/UsersList.vue";

const isLoading = ref<boolean>(true);
const users = ref<User[]>([]);

onMounted(() => {
  isLoading.value = true;
  setTimeout(() => {
    seedUsers();
    isLoading.value = false;
  }, 2000);
});

const seedUsers = () => {
  users.value.push({
    id: 1,
    email: "admin@gmail.com",
    is_admin: true,
    name: "Super Admin",
    phone: "01023234571",
  });

  users.value.push({
    id: 2,
    email: "customer1@gmail.com",
    is_admin: false,
    name: "Customer 1",
    phone: "01115610047",
  });

  users.value.push({
    id: 3,
    email: "customer2@gmail.com",
    is_admin: false,
    name: "Customer 2",
    phone: "0535725886",
  });
};
</script>

<style scoped></style>
