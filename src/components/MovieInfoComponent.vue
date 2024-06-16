<script setup>
let props = defineProps([
  "index",
  "ImagePath",
  "moveType",
  "desc",
  "UA",
  "year",
  "language",
]);
</script>
<template>
  <div class="info-box">
    <img :src="ImagePath" /><img />
    <div class="movie-Information">
      <div class="btn-section">
        <div class="watch-now-btn">
          <button><img src="../../public/play.svg" alt="" />Watch Now</button>
        </div>
        <div class="button-box">
          <button><img src="../../public/plus.svg" alt="" /></button>
        </div>
      </div>
      <ul class="ratings">
        <li>{{ year }}</li>
        <li><span></span></li>
        <li>{{ language }}</li>
        <li><span></span></li>
        <li>U/A {{ UA }}+</li>
        <li><span></span></li>
        <li>{{ moveType }}</li>
      </ul>
      <p class="movie-info">
        {{ desc }}
      </p>
    </div>
  </div>
</template>
<style scoped>
.info-box {
  width: 350px;
  height: 411px;
  background-color: firebrick;
  position: absolute;
  opacity: 0;
  transition: 0.4s;
  transition-delay: 0.8s;
  overflow: hidden;
}
.info-box:hover {
  opacity: 1;
  transform: translateX(-10%);
}
.info-box img {
  width: 100%;
  top: -30%;
  position: absolute;
}
.movie-Information {
  width: 100%;
  height: 200px;
  background-color: black;
  position: absolute;
  bottom: 0;
  z-index: 10;
  box-shadow: 0px -26px 21px 0px black;
}

.btn-section {
  /* background-color: aliceblue; */
  display: flex;
  justify-content: center;

  align-items: center;
  gap: 10px;
}
.watch-now-btn button {
  padding: 10px 40px;
  font-weight: 700;
  color: black;
  font-size: 19px;
  border: none;
  background-color: #69b6ff;
  border-radius: 5px;
  position: relative;
}
.watch-now-btn button img {
  width: 12px;
  top: 15px;
  left: 14%;
}
.button-box button {
  background-color: #3d95e9;
  border-radius: 5px;
  position: relative;
  border: none;
  font-weight: 700;
  font-size: 19px;

  padding: 20px 20px;
}
.button-box button img {
  top: 0;
  right: 0;
  width: 25px;
  transform: translate(-30%, 30%);
}
.ratings {
  display: flex;
  gap: 10px;
  justify-content: center;
  align-items: center;
  margin-top: 15px;
  font-weight: 700;
}
.ratings li span {
  width: 10px;
  height: 10px;
  display: block;
  background-color: white;
  border-radius: 50%;
  font-weight: 600;
}
.movie-info {
  padding: 10px;
  font-weight: 300;
}
button {
  cursor: pointer;
}
</style>
