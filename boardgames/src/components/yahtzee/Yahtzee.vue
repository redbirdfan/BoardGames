<script setup>
    import { ref } from 'vue';

    import './Yahtzee.css'
    import DiceRoll from './DiceRoll.vue';
    import Scorecard from './Scorecard.vue';

    const dice =ref([0, 0, 0, 0, 0])
    const lockedDice=([false, false, false, false, false])
    let turnRoll = 1;

    const updateDice = (newDice)=>{
        if(turnRoll < 3){
        dice.value = newDice
        return turnRoll = turnRoll+1
        console.log(turnRoll)
        } else { 
            console.log("max turns reached")
        }
    }

    const diceLock = (index)=> {
        if(turnRoll >= 1 ){
           if(lockedDice[index] === true){
                lockedDice[index] = false
                console.log(index, lockedDice[index])
                
            } else lockedDice[index] = true
        }
    }
</script>

<template>
    <div class="dice-container">
       <div 
        v-for="(die, index) in dice" 
        :key="index" 
        class="dice-face"
        :class="{ 'is-locked': lockedDice[index] }"
        @click="diceLock(index)"
        >
        {{ die === 0 ? 'Yahtzee' : die }}
       </div>
    </div>

    <DiceRoll @diceRolled="updateDice" :rollCount="turnRoll"/>

    <Scorecard />
            
</template>