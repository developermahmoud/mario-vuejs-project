<template>
  <div class="relative overflow-x-auto">
    <table
      class="w-full text-sm text-left rtl:text-right text-gray-500 dark:text-gray-400"
    >
      <thead
        class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400"
      >
        <tr>
          <th scope="col" class="px-6 py-3">#</th>
          <th scope="col" class="px-6 py-3">ID</th>
          <th scope="col" class="px-6 py-3">Name</th>
          <th scope="col" class="px-6 py-3">Email</th>
          <th scope="col" class="px-6 py-3">Phone</th>
          <th scope="col" class="px-6 py-3">Is Admin</th>
          <th scope="col" class="px-6 py-3"></th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="(user, index) in users"
          :key="user.id"
          class="bg-white border-b dark:border-gray-700"
        >
          <td class="px-6 py-4">{{ index + 1 }}</td>
          <td class="px-6 py-4">{{ user.id }}</td>
          <td class="px-6 py-4">{{ user.name }}</td>
          <td class="px-6 py-4">{{ user.email }}</td>
          <td class="px-6 py-4">{{ user.phone }}</td>
          <td class="px-6 py-4">{{ user.is_admin }}</td>
          <td class="px-6 py-4">
            <div class="flex gap-2">
              <button
                type="button"
                class="focus:outline-none text-white bg-red-700 hover:bg-red-800 focus:ring-4 focus:ring-red-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-red-600 dark:hover:bg-red-700 dark:focus:ring-red-900"
              >
                Delete
              </button>
              <button
                type="button"
                class="focus:outline-none text-white bg-yellow-400 hover:bg-yellow-500 focus:ring-4 focus:ring-yellow-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:focus:ring-yellow-900"
              >
                Edit
              </button>
            </div>
          </td>
        </tr>
        <tr>
          <td class="text-center">#</td>
          <td>
            <input
              type="text"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              placeholder="Enter ID"
            />
          </td>
          <td>
            <input
              type="text"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              placeholder="Enter Name"
            />
          </td>
          <td>
            <input
              type="text"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              placeholder="Enter Email"
            />
          </td>
          <td>
            <input
              type="text"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              placeholder="Enter Phone"
            />
          </td>
          <td>
            <label
              class="relative mt-5 inline-flex items-center mb-5 cursor-pointer"
            >
              <input type="checkbox" value="" class="sr-only peer" />
              <div
                class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-4 peer-focus:ring-blue-300 dark:peer-focus:ring-blue-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full rtl:peer-checked:after:-translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:start-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:w-5 after:h-5 after:transition-all dark:border-gray-600 peer-checked:bg-blue-600"
              ></div>
              <span
                class="ms-3 text-sm font-medium text-gray-900 dark:text-gray-300"
                >Is Admin</span
              >
            </label>
          </td>
          <td>
            <button
              type="button"
              class="focus:outline-none w-full text-white bg-green-700 hover:bg-green-800 focus:ring-4 focus:ring-green-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
            >
              Add New User
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang="ts" setup>
import type { User } from "../../interfaces/user";
import { defineProps } from "vue";

defineProps({
  users: {
    type: Array<User>,
    required: true,
  },
});
</script>

<style scoped></style>
