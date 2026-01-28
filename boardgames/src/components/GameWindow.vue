<script setup>
  import {defineProps} from 'vue'
  import Yahtzee from './yahtzee/Yahtzee.vue';
  
  defineProps(['chosen']);

</script>

<template>
  <div class="game-Container">
    
      <div v-if="chosen==='Yahtzee'">
        <Yahtzee />
      </div>
      <img v-else-if="chosen==='Hangman'" :src="'https://tse3.mm.bing.net/th/id/OIP.939jb7r6e16TCTIijh10vwHaEW?pid=Api&P=0&h=180o'">

      <img v-else-if="chosen==='Chess'" :src="'https://tse2.mm.bing.net/th/id/OIP.tZHJpkzFtBOyY2haH9BUxQHaEK?pid=Api&P=0&h=180'">

      <img v-else-if="chosen==='Tic-Tac-Toe'" :src="'https://i.pinimg.com/originals/94/e0/26/94e02699fe51fe20bcec409330e0a716.jpg'" >
  
      <img v-else="" :src="'https://tse1.mm.bing.net/th/id/OIP.YDi7Z5oCmAwqc0JB5bpO_gHaFj?pid=Api&P=0&h=180'" translate="1px, 0,0">
  </div>

</template>

