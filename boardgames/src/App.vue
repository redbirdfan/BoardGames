<script setup>
  import {ref} from 'vue'; 
  import DropDownMenu from './components/DropDownMenu.vue';
  import GameWindow from './components/GameWindow.vue';
  import './CSS/page.css'
  import './CSS/GameWindow.css'
  import Darkmode from './components/DarkMode.vue';

  const selectedGame = ref('');
  const currentMode = ref('light')

</script>

<template>
  <v-app><div :class="currentMode + '-mode'">

    <header class="header">
      <DropDownMenu v-model="selectedGame"/>
      <Darkmode v-model:colorMode="currentMode" />
    </header>
  
    <div class="game-Container">
      <GameWindow :chosen="selectedGame" />
    </div>

  </div>
  </v-app>
</template>

