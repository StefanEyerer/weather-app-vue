<script setup>
import { defineEmits } from "vue";
import DataItem from "./DataItem.vue";

defineProps({ datapoints: Array });
const emit = defineEmits(["onReset"]);

const handleReset = () => {
  emit("onReset");
};
</script>

<template>
  <section>
    <DataItem v-for="datapoint of datapoints" :datapoint="datapoint" />
    <button
      v-if="datapoints.length"
      class="w-full cursor-pointer rounded-md p-2 text-2xl bg-blue-900"
      @click="handleReset"
    >
      Reset Data
    </button>
  </section>
</template>

<style scoped></style>
