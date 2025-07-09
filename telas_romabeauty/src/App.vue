<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'

import { ref } from 'vue'

const menuAberto = ref(false)
const opcaoSelecionada = ref(null)

function toggleMenu() {
  menuAberto.value = !menuAberto.value
  opcaoSelecionada.value = null // reseta submenu ao abrir
}

function selecionarOpcao(opcao) {
  opcaoSelecionada.value = opcao
}

</script>


<template>
  <div class="inicio">

    <div class="menu-container">
      <div class="menu" @click="toggleMenu">
        <i class="fa-solid fa-bars"></i>

        <div v-if="menuAberto" class="dropdown-menu">
          <ul>
            <li :class="{ selecionado: opcaoSelecionada === 'perfume' }" @click.stop="selecionarOpcao('perfume')">
              Perfume
            </li>
            <li :class="{ selecionado: opcaoSelecionada === 'creme' }" @click.stop="selecionarOpcao('creme')">
              Creme
            </li>
            <li :class="{ selecionado: opcaoSelecionada === 'desodorante' }"
              @click.stop="selecionarOpcao('desodorante')">
              Desodorante
            </li>
          </ul>


          <div v-if="opcaoSelecionada === 'perfume'" class="submenu">
            <ul>
              <li>Body Splash</li>
              <li>Colônia</li>
              <li>maria</li>
            </ul>
          </div>

          <div v-if="opcaoSelecionada === 'creme'" class="submenu">
            <ul>
              <li>Hidratante</li>
              <li>Nutritivo</li>
              <li>Anticelulite</li>
            </ul>
          </div>

          <div v-if="opcaoSelecionada === 'desodorante'" class="submenu">
            <ul>
              <li>Aerosol</li>
              <li>Bastão</li>
              <li>maria</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="nome-logo">
        <h2>ROMA</h2>
      </div>

      <i class="fa-solid fa-magnifying-glass"></i>
      <i class="fa-solid fa-user"></i>
      <i class="fa-solid fa-bag-shopping"></i>
    </div>

    <h1>ROMA BEAUTY</h1>
  </div>




  <main>
  </main>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css"
    integrity="sha512-Evv84Mr4kqVGRNSgIGL/F/aIDqQb7xQ2vcrdIwxfjThSH8CSR7PBEakCr51Ck+w+/U6swU2Im1vVX0SVk9ABhg=="
    crossorigin="anonymous" referrerpolicy="no-referrer" />
</template>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link
  href="https://fonts.googleapis.com/css2?family=Anton+SC&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&family=Montserrat:ital,wght@0,100..900;1,100..900&family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Work+Sans:ital,wght@0,100..900;1,100..900&display=swap"
  rel="stylesheet">
</link>

<style scoped>
/*MENU*/
.menu-container {
  position: fixed;
  top: 0;
  width: 100%;
  max-width: 1530px;
  height: 70px;

  display: flex;
  align-items: center;
  z-index: 999;
  background-color: #ffffff;
  box-shadow: 2px 2px 5px #a3b1c6, -2px -2px 5px #ffffff;


}


.menu {
  margin-left: 20px;
}

.menu-container>.menu:first-child {
  margin-left: 40px;
}


.menu-container i:last-child {
  margin-right: 60px;
}


.menu-container i {
  font-size: 1.5rem;
  color: #000;
  margin: 0 10px;
}

.menu-container h2 {
  font-family: "Playfair Display", serif;
  font-size: 2rem;
  font-weight: 700;
  margin: 0;
}

/* Exemplo para espaçar os elementos com mais controle */
.menu {
  display: flex;
  align-items: center;
}

.nome-logo {
  display: flex;
  align-items: center;
  justify-content: center;
  flex: 1;
  text-align: center;
}


/*MENU*/



/*IniCIO*/
.inicio {
  position: relative;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* H1 por baixo */
.inicio h1 {
  font-family: "Playfair Display", serif;
  font-weight: 700;
  font-size: 12rem;
  position: relative;
  top: 40px;
  animation: primeiranimation 1s ease 0.3s forwards;
  z-index: -1;
}




@keyframes primeiranimation {
  0% {
    transform: scale(1);
  }


  100% {
    color: #feb7d9;
    opacity: 0.4;
    transition: ease 1s;
  }
}

/*menu*/
.dropdown-menu {
  position: absolute;
  top: 70px;
  width: 400px;
  left: 0;
  background-color: #ffffff;
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 0 0 10px 0;
  padding: 10px 20px;
  z-index: 1000;
}

.dropdown-menu ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.dropdown-menu li {
  padding: 8px 0;
  cursor: pointer;
  font-family: 'Poppins', sans-serif;
}

.dropdown-menu li:hover {
  color: #feb7d9;
  font-weight: bold;
}

/*seleção-menu*/

.dropdown-menu li.selecionado {
  background-color: #feb7d95f;
  color: #ffffff;
  font-weight: bold;
  transition: background-color 0.5s ease, color 0.5s ease;
  border-radius: 5px;
}



/*seleção-menu*/


.submenu {
  position: absolute;
  top: 0;
  left: 100%;
  background-color: #ffffff;
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 0 10px 10px 10px;
  padding: 10px 20px;
  min-width: 200px;
  z-index: 1001;
}

.submenu ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.submenu li {
  padding: 8px 0;
  cursor: pointer;
  font-family: 'Poppins', sans-serif;
}

.submenu li:hover {
  color: #feb7d9;
  font-weight: bold;
}


/*IniCIO*/
</style>
