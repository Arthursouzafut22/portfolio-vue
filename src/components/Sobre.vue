
<script setup>
import { reactive } from 'vue';

const dados = reactive([
  'Nome:',
  'Data de nascimento:',
  'Endereço:',
  'CEP:',
  'E-mail:',
  'Telefone:'
]);

const info = reactive([
  'Arthur Souza',
  '26 de Outubro de 2000',
  'Rua del pret',
  '33400000',
  '31-983262026'
]);

</script>


<template>

<main class="sobre">
        <img class="boneco2" src="/src/assets/teste.png" alt="" />
        <div class="sobre-2">
          <div class="conteiner-sobre">
            <h1>Sobre mim</h1>
            <span class="details-sobre">Sobre</span>
            <p class="sobre-paragrafo">
              Um pequeno rio chamado Duden passa por seu lugar e abastece-o com
              a regelialia necessária.
            </p>
          </div>
          <div class="info-sobre">
            <div class="conteiner-info">
              <span v-for="dado in dados" :key="dado">
                {{ dado }}
              </span>
            </div>
            <div class="conteiner-info2">
              <span v-for="infos in info" :key="infos">
                {{ infos }}
              </span>
              <span class="email">Arthursouzafut22@gmail.com</span>
            </div>
          </div>
          <p class="sobre-paragrafo2">
            <span>100%</span> Motivado por desafios
          </p>
          <div class="cont-curri">
            <a class="btn-curriculo" href="#">Baixar currículo</a>
          </div>
        </div>
      </main>
    
</template>

<style scoped>

.sobre {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    max-width: 100%;
    padding: 1.25rem;
}

.sobre-2 {
    max-width: 100%;
    width: 700px;
}
.conteiner-sobre {
    position: relative;
    max-width: 100%;
}
.sobre-2 h1 {
    font-size: 3.125rem; 
    color: #FFFCE1;
    margin: 0;
    animation: animate .50s forwards;
}
.details-sobre {
    display: block;
    font-size: 6.25rem;
    font-weight: bolder;
    color: #1A1A1A;
    position: absolute;
    margin: 0px;
    top: 0;
    z-index: -1;
    animation: animate .80s forwards;
}
.sobre-paragrafo {
    font-size: 1.125rem;
    color: #5C5C5C;
    animation: animate .90s forwards;
}
.info-sobre {
    display: flex;
    align-items: center;
    margin-top: 15px;
}
.info-sobre span {
    display: block;
    margin: 0;
}
.conteiner-info {
    color: white;
    margin-right: 20px;
    width: 100%;
}
.conteiner-info span {
    font-size: 1.25rem;
    font-weight: 700;
    color: #FFFCE1;
    margin-bottom: 10px;
    animation: animate .90s forwards;
}
.conteiner-info2 {
    width: 100%;
}
.conteiner-info2 span {
    color: #5C5C5C;
    font-size: 1.25rem;
    font-weight: 500;
    margin-bottom: 10px;
    animation: animate .90s forwards;
}
.sobre-paragrafo2 {
    color: #FFFCE1;
    font-size: 1.25rem;
    animation: animate .70s forwards;
}
.sobre-paragrafo2 span {
    font-size: 1.4375rem;
    color:#FFBD39;
    animation: animate .50s forwards;
}
.btn-curriculo {
    display: inline-block;
    font-family: 'Poppins', sans-serif;
    text-transform: uppercase;
    color: black;
    text-decoration: none;
    margin-right: 7px;
    background-color: #FFBD39;
    padding: 0.9375rem 1.25rem;
    border-radius: 15px;
    animation: animate .90s forwards;
}
.email {
  word-wrap: break-word;
  overflow-wrap: break-word;
}
.boneco2 {
    max-width: 100%;
}




@media (max-width:480px) {
    .sobre-2 h1 {
        font-size: 2.0625rem;
    }
    .boneco2 {
        display: none;
    }
    .details-sobre {
        font-size: 2.5rem;
    }
    .sobre-paragrafo {
        font-size: 0.9375rem;
    }
    .conteiner-info {
        margin-right: 6px;
    }
    .conteiner-info span {
        font-size: 0.875rem;
        margin-bottom: 12px;
    }
    .conteiner-info2 span {
        margin-bottom: 15px;
        font-size: 0.875rem;
    }
    .btn-curriculo {
        padding: 0.625rem 1.25rem;
    }
}

@media (min-width:481px) and (max-width:991px) {
    .boneco2 {
        margin: 0 auto;
    }
    .sobre-2 {
        margin: 0 auto;
    }
    .sobre-paragrafo2 {
       text-align: center;
    }
    .conteiner-sobre {
        margin-top: 20px;
    }
    .cont-curri {
       display: flex;
       justify-content: center;
       align-items: center;
    }
}

@media (min-width:992px) {
    .sobre {
        flex-wrap: nowrap;
    }
}

</style>


