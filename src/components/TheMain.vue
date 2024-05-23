
<script setup>
import { reactive } from "vue";

const imgs = reactive([
  "/src/assets/logotipo-do-linkedin.png",
  "/src/assets/placa-do-github.png",
  "/src/assets/enviar.png",
]);
</script>

<template>
  <main class="main">
    <div class="conteiner-intro">
      <span class="span-intro">ola!</span>
      <h1>
        Sou Arthur <span>Desenvolvedor Frontend</span> baseado em desafios
      </h1>
      <div class="conteiner-btns">
        <img :src="img" alt="logos" v-for="img in imgs" :key="img"/>
      </div>
    </div>
    <img class="boneco" src="/src/assets/teste.png" alt="anta" />
  </main>
</template>

<style scoped>
.main {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  max-width: 100%;
}

.conteiner-intro {
  max-width: 100%;
  width: 500px;
  padding: 20px;
}

.conteiner-intro span {
  display: block;
  color: #ffbd39;
}

.conteiner-intro h1 {
  font-family: "Poppins", sans-serif;
  font-size: 55px;
  color: #fffce1;
  margin: 0;
  animation: animate 0.6s forwards;
}

.span-intro {
  font-family: "Poppins", sans-serif;
  font-size: 30px;
  margin: 0;
  animation: animate 0.5s forwards;
}

.conteiner-btns {
  display: flex;
  align-items: center;
  gap: 25px;
  margin-top: 12px;
}

.conteiner-btns img {
  display: block;
  max-width: 70px;
  cursor: pointer;
}

.boneco {
  max-width: 100%;
}

@media (max-width: 480px) {
  .span-intro {
    font-size: 18px;
  }

  .conteiner-intro h1 {
    font-size: 30px;
  }
  .conteiner-btns {
    justify-content: start;
    gap: 10px;
  }
  .conteiner-btns img {
    max-width: 50px;
  }
}

@media (min-width: 481px) and (max-width: 991px) {
  .span-intro {
    font-size: 18px;
  }

  .conteiner-intro {
    margin: 15px auto 0px auto;
    text-align: center;
  }
  .conteiner-intro h1 {
    font-size: 30px;
  }
  .conteiner-btns {
    margin: 12px auto;
    width: 300px;
    justify-content: center;
  }

  .boneco {
    margin: 0 auto;
  }
}
</style>


