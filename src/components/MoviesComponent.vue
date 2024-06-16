<script setup>
import SliderComponent from "./SliderComponent.vue";
import HeaderComponent from "./HeaderComponent.vue";
import json from "../data/data.json";
import { ref } from "vue";
const data = ref(json);
let optionName = ref("home");
</script>
<template>
  <HeaderComponent :optionName="optionName" />
  <div class="movies-container">
    <SliderComponent
      v-for="(item, index) in data"
      :name="index"
      :MoviesData="item"
      :key="index"
    />
  </div>
</template>
<style scoped>
.movies-container {
  width: 100%;
  padding: 30px 0 20px 60px;
}
</style>
