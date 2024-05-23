
<script setup>
import Hamburgue from "./Hamburgue.vue";
import { reactive, ref } from "vue";

const navs = reactive([
  "Sobre",
  "Serviços",
  "Projetos",
  "Contato",
]);

const showMenu = ref(true);


const toggleMenu = () => {
  return (showMenu.value = !showMenu.value);
};
</script>


<template>
  <header class="header">
    <a class="logo" href="#">portfolio</a>
    <nav class="nav" :class="{active: showMenu}">
      <ul class="menu">
        <li><a class="yello" href="#">Home</a></li>
        <li v-for="nav in navs" :key="nav">
          <a href="#">
            {{ nav }}
          </a>
        </li>
      </ul>
    </nav>
    <button class="btn-mobile" aria-expanded="false" @click="toggleMenu">
      Menu 
    </button>
  </header>
</template>

<style scoped>
.header {
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 100%;
  margin: 0 auto;
}

.logo {
  font-family: "Poppins", sans-serif;
  font-size: 30px;
  font-weight: bolder;
  text-decoration: none;
  color: #fffce1;
  display: block;
}

.menu {
  display: flex;
  align-items: center;
  gap: 30px;
}

.yello {
  font-family: "Poppins", sans-serif;
  font-size: 18px;
  color: #ffbd39;
  padding-bottom: 4px;
  text-decoration: none;
  border-bottom: 3px solid #ffbd39;
}

.menu li a:not(.yello) {
  font-family: "Poppins", sans-serif;
  font-size: 18px;
  text-decoration: none;
  color: #fffce1;
  transition: 0.3s;
  padding-bottom: 7px;
  position: relative;
}

.menu li a:not(.yello)::before {
  content: "";
  position: absolute;
  left: 50%;
  bottom: 0;
  display: block;
  width: 0%;
  height: 3px;
  background-color: #ffbd39;
  transition: 0.5s;
  transform: translateX(-50%);
}

.menu li a:hover::before {
  width: 100%;
}

.btn-mobile {
  display: none;
  /* background-color: transparent; */
  background: #ffbd39;
  padding: 10px;
  border: none;
}

@media (max-width: 991px) {
  .logo {
    font-size: 20px;
  }
  .btn-mobile {
    display: block;
  }
  .menu {
    flex-direction: column;
    position: fixed;
    border: 1px solid wheat;
    gap: 20px;
    padding: 25px;
    right: 2px;
    top: 65px;
  }
  .active {
    display: none;
  }
}

</style>