<script setup>
import { ref } from "vue";
import movieBoxComponent from "./MovieBoxComponent.vue";
let props = defineProps(["name", "MoviesData"]);
let sliderDiv = ref();
const vFormatDiv = {
  mounted(el, binding) {
    sliderDiv = el;
    console.log(el.scrollLeft);
  },
};
function leftBtnCall() {
  sliderDiv.style.scrollBehavior = "smooth";
  sliderDiv.scrollLeft -= 500;
}
function rightBtnCall() {
  sliderDiv.style.scrollBehavior = "smooth";
  sliderDiv.scrollLeft += 400;
  leftBtnVisible.value = sliderDiv.scrollLeft >= 0 ? true : false;
}
</script>
<template>
  <div class="box">
    <div class="box-header">
      <h2 class="slider-title">{{ name }}</h2>
      <p class="view-all-tag">View All</p>
    </div>
    <button @click="leftBtnCall" class="btn left-btn">
      <div class="shadow"></div>
      <img src="../../public/rightbtnicon .svg" alt="" />
    </button>
    <div v-formatDiv class="movies-box-cotnainer">
      <movieBoxComponent :MoviesData="MoviesData" />
    </div>
    <button @click="rightBtnCall" class="btn right-btn">
      <div class="shadow"></div>
      <img src="../../public/leftbtnicon .svg" alt="" />
    </button>
  </div>
</template>
<style scoped>
.box {
  /* border: 2px solid red; */
  position: relative;
}
.slider-title {
  margin-bottom: 20px;
}
.box-header {
  display: flex;
  justify-content: space-between;
}
.view-all-tag {
  padding-right: 20px;
  color: #d3d3d3cc;
}
.movies-box-cotnainer {
  display: grid;
  gap: 20px;
  /* font-size: 0px; */
  overflow: hidden;
  overflow-x: auto;
  margin-bottom: 30px;
  scrollbar-width: none;
  grid-template-columns: repeat(14, 1fr);
}
.movies-box-cotnainer::-webkit-scrollbar {
  display: none;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}
.btn {
  height: 411px;
  width: 4vw;
}
.left-btn {
  position: absolute;
  z-index: 10;

  background-image: linear-gradient(to right, #1c1c1e 10%, #12121200);
  background-color: transparent;
  border: none;
  left: 0;
}
.right-btn {
  background-image: linear-gradient(to left, #1c1c1e 10%, #12121200);
  background-color: transparent;
  position: absolute;
  z-index: 10;
  right: 0;
  top: 10%;
  border: none;
}
.btn img {
  width: 20px;
  opacity: 0.8;
}
.btn {
  cursor: pointer;
}
.shadow {
  width: 100%;
  height: 100%;
  position: absolute;
  background-color: transparent;
  top: 0;
  box-shadow: 8px -2px 20px 10px #000000cc;
}
</style>
