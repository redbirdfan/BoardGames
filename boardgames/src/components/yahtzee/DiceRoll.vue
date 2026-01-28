<script setup>

import {ref} from 'vue';

const emit = defineEmits(['diceRolled'])

const dice = ref([0, 0, 0, 0, 0])

const rollDice = () =>{

    const newDice = dice.value.map(() => {
        const result = Math.floor(Math.random() * 6) + 1
        return result;
    })

    dice.value=newDice

    emit('diceRolled', newDice)
}

</script>

<template>
    <div class="roll-dice">
        <button @click='rollDice'>Roll Dice</button>
    </div>
</template>