<script setup>
    import { ref } from 'vue';

    import './Yahtzee.css'
    import DiceRoll from './DiceRoll.vue';

    const dice =ref([0, 0, 0, 0, 0])
    
    const updateDice = (newDice)=>{
        dice.value = newDice
        console.log(newDice)
    }
</script>

<template>
    <div class="dice-container">
       <div v-for="(die, index) in dice" :key="index" class="dice-face">
        {{ die === 0 ? '?' : die }}
       </div>
    </div>

    <DiceRoll @diceRolled="updateDice" />

    <div class="score-container">
            <p>Scorecard</p>
    </div>

    
</template>