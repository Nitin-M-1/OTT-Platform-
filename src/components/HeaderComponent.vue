<script setup>
import { ref } from "vue";
import "../assets/main.css";
let props = defineProps(["optionName"]);
</script>
<template>
  <header class="main-header">
    <div class="header-left-container">
      <img src="../../public/indee-logo.svg" alt="" />
      <ul class="menu">
        <li :class="optionName == 'home' ? 'active' : ''">Home</li>
        <li :class="optionName == 'Tv Show' ? 'active' : ''">Tv Shows</li>
        <li :class="optionName == 'Movies' ? 'active' : ''">Movies</li>
        <li :class="optionName == 'Recently Added' ? 'active' : ''">
          Recently Added
        </li>
        <li>
          <a
            href="https://www.figma.com/board/OhxF3vCdH92JoRRcQUlrHX/Untitled?node-id=0-1&t=vnQ0toCoy1g9Q1tX-1"
            target="_blank"
            >( ReadMe)</a
          >
        </li>
      </ul>
    </div>
    <div class="header-right-container"></div>
  </header>
</template>
<style scoped>
.main-header {
  width: 100%;
  height: 90px;
  background-color: black;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 60px;
}
.menu {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 26px;
  font-size: 20px;
  margin-left: 72px;
  font-weight: 700;
}
li {
  color: var(--light-white);
  cursor: pointer;
  transition: 0.2s;
}
li:hover {
  transform: scale(1.1);
}
.header-left-container {
  display: flex;
  justify-content: center;
  align-items: center;
}
.btn {
  width: 90px;
  height: 40px;
  margin: 0 10px;
  border: none;
  font-size: 20px;
  font-weight: 700;
  border-radius: 5px;
  cursor: pointer;
}
.login-btn {
  background-color: var(--loginBtn-color);
}
.signin-btn {
  background-color: var(--signIn-color);
}
.active {
  color: white;
  padding-bottom: 5px;
  border-bottom: 3px solid var(--signIn-color);
}
</style>
