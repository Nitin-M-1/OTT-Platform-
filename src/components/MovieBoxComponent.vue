<script setup>
import { ref } from "vue";
import MovieInfoComponent from "./MovieInfoComponent.vue";
let showInfo = ref(false);

let props = defineProps(["MoviesData"]);
</script>
<template>
  <div
    @mouseover="showInfo = true"
    @mouseleave="showInfo = false"
    class="move-box"
    v-for="(item, index) in MoviesData"
    :key="index"
  >
    <MovieInfoComponent
      v-if="showInfo"
      :ImagePath="item.imagePath"
      :year="item.year"
      :language="item.language"
      :UA="item.UA"
      :moveType="item.movieType"
      :desc="item.desc"
      class="info-box"
    />

    <img :src="item.imagePath" alt="" />
    <div v-if="item.new" class="new-box">
      <span>New</span>
    </div>
    <div class="movieName">{{ item.name }}</div>
  </div>
</template>
<style scoped>
.move-box {
  width: 227px;
  height: 411px;
  background-image: linear-gradient(to right, #1c1c1e, #121212);
  border-radius: 10px;
  box-shadow: 0px 4px 5px #00000083;
  cursor: pointer;
  transition: 0.3s;
}
.move-box:hover {
  transform: scale(1.1);
}

.move-box img {
  width: 100%;
}
.new-box {
  padding: 2px 10px;
  margin: 5px 0 5px 5px;
  background-color: var(--orange);
  width: max-content;
  border-radius: 3px;
}
.new-box span {
  color: black;
  font-weight: 700;
}
.movieName {
  margin: 5px;
  font-size: 15px;
}
.info-box {
  transform: translateX(5%);
  position: absolute;
}
</style>
