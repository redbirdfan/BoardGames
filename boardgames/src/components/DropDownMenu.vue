

<template>

    <select v-model="selectedGame" id="gameSelection" class="gameMenuSelection">
        <option value="" disabled selection>It's Game Night!</option>
        <option value="Chess">Chess</option>
        <option value="Hangman">Hangman</option>
        <option value="Yahtzee">Yahtzee</option>
        <option vlaue="Tic-Tac-Toe">Tic-Tac-Toe</option>
    </select>
            
</template>

<script>
    
    import '../CSS/Page.css'

    export default {
    data() {
        return {
            selectedGame: "",
           }
        }
    }
</script>
