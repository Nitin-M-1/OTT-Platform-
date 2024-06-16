<script setup>
import { ref } from "vue";
let removeBox = ref(false);
</script>
<template>
  <div :style="{ right: removeBox ? '-1000px' : '0' }" id="features-box">
    <h1 class="key-features-header">Key Features</h1>
    <hr />
    <div class="features-list">
      <h2>1)Fast Loding time</h2>
      <h2>2)Easy to optimize code</h2>
      <h2>3)Easy for scalable</h2>
    </div>
    <hr />
    <h1 class="key-features-header">Disadvantages</h1>

    <div class="disadvantages-list">
      <h2>1)Not-Responsive</h2>
      <h2>2)Small minor animation bug</h2>
      <h3>( can be easily fixed..but need more time)</h3>
    </div>
    <hr />
    <h1 class="key-features-header">Reference</h1>

    <div class="linkes-sections">
      <a
        href="https://www.figma.com/design/AwWX1OB0civo5zDuLJAZTr/Assignment---Frontend---May-2024-(Copy)-(Copy)?m=dev&node-id=0-1&t=SHWmFECB6oPbPGf8-1"
        target="_blank"
        >Figma design..link</a
      >
      <a
        href="https://www.figma.com/board/OhxF3vCdH92JoRRcQUlrHX/Untitled?node-id=1-164&t=IkY2qXwru8SuyZW8-1"
        target="_blank"
        >Webpage Blueprint..link</a
      >
    </div>
    <button @click="removeBox = true">X</button>
  </div>
</template>

<style>
#features-box {
  width: 400px;
  position: absolute;
  background-color: white;
  top: 0;
  right: 0;
  transform: translateX(-50%);
  z-index: 100;
  padding: 10px 20px;
  transition: 0.6s;
}
h1,
h2,
h3 {
  color: black;
}
.key-features-header {
  color: black;
  text-align: center;
  font-weight: 800;
  padding-bottom: 10px;
}
a {
  color: black;
  font-size: 20px;
  text-align: center;
  text-decoration: underline;
  width: 100%;
  display: inline-block;
  text-align: center;
  padding: 10px;
}
button {
  font-size: 20px;
  padding: 10px 20px;
  display: inline-block;
  position: absolute;
  top: 0;
  right: 0;
  border: none;
  background-color: black;
  font-weight: 800;
  border-radius: 5px;
  cursor: pointer;
}
.goFar {
  background-color: firebrick;
}
</style>
