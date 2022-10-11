<script setup>
import { ref } from "vue";
import { requestWeatherData } from "../utils/request-weather-data";
import DataList from "./DataList.vue";
import Search from "./Search.vue";

const weatherData = ref([]);

const handleSubmit = async (location) => {
  const result = await requestWeatherData(location);
  weatherData.value = [...weatherData.value, result];
};

const handleReset = () => {
  weatherData.value = [];
};
</script>

<template>
  <main class="flex-1 w-1/2 m-auto py-8 px-4">
    <div class="flex flex-col gap-12">
      <h1 class="text-center text-4xl">
        Get current weather data for any location!
      </h1>
      <Search @on-submit="handleSubmit" />
      <DataList :datapoints="weatherData" @on-reset="handleReset" />
    </div>
  </main>
</template>

<style scoped></style>
