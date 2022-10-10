<script setup>
import { ref } from "vue";
import { data } from "../mock-data";
import DataList from "./DataList.vue";
import Search from "./Search.vue";

const weatherData = ref(data);
</script>

<template>
  <main class="flex-1 w-1/2 m-auto py-8 px-4">
    <div class="flex flex-col gap-12">
      <h1 class="text-center text-4xl">
        Get current weather data for any location!
      </h1>
      <Search />
      <DataList :datapoints="weatherData" />
    </div>
  </main>
</template>

<style scoped></style>
