<script setup>
import { callWithAsyncErrorHandling } from 'vue';

    let rollScore = 0;
    
    let one = 0;
    let two = 0;
    let three = 0;
    let four = 0;
    let five = 0;
    let six = 0;
    
    let softTotal = one+two+three+four+five+six;
    let bonusTotal = 0;
    
    if(softTotal >= 63){
        bonusTotal = 35
    }

    let threeKind = 0;
    let fourKind = 0;
    let smallStraght = 35;
    let largeStraight = 0;
    let chance = 0;
    let fullHouse = 0;
    let yahtzeeRoll = 0;
    let bonusYahtzee = 0;

    let upperTotal = softTotal+bonusTotal;
    let lowerTotal = threeKind+fourKind+smallStraght+largeStraight+fullHouse+chance+yahtzeeRoll+bonusYahtzee
    let totalScore = lowerTotal+upperTotal;
</script>

<template>
    <div class="score-container">
        <p>Total Ones:</p>
        <p>Total Twos:</p>
        <p>Total Threes:</p>
        <p>Total Fours:</p>
        <p>Total Fives:</p>
        <p>Total Sixes:</p>
        <p>Upper Total:</p>
        <p>Bonus > (63):</p>
        <p>Upper Total:</p>
    </div>

    <div class="score-container">
        <p value="one">{{ one }}</p>
        <p value="two"> {{ two }}</p>
        <p value="three">{{ three }}</p>
        <p value="four">{{ four }}</p>
        <p value="five"> {{ five }}</p>
        <p value="six"> {{ six }}</p>
        <p value="softTotal">{{ softTotal }}</p>
        <p value="bonusTotal">{{ bonusTotal }}</p>
        <p value="upperTotal">{{  upperTotal }}</p>
    </div>

    <div class="score-container" style="padding-left: 25px;">
        <p>3 of a Kind:</p>
        <p>4 of a Kind:</p>
        <p>Small Stright:</p>
        <p>Large Straight:</p>
        <p>Full House:</p>
        <p>Chance:</p>
        <p>Yahtzee:</p>
        <p>Bonus Yahtzee:</p>
        <p>Lower Total:</p>
    </div>
    
        <div class="score-container" style="padding-left: 25px;">
        <p value="threeKind">{{ threeKind }}</p>
        <p value="fourKind">{{ fourKind }}</p>
        <p value="smallStraight">{{ smallStraght }}</p>
        <p value="largeStraight">{{ largeStraight }}</p>
        <p value="fullHouse">{{ fullHouse }}</p>
        <p value="chance"> {{ chance }}</p>
        <p value="yahtzeeRoll">{{ yahtzeeRoll }}</p>
        <p value="bonusYahtzee"> {{ bonusYahtzee }}</p>
        <p value="lowerTotal">{{ lowerTotal }}</p>
    </div>

    <div>
        <p value="totalScore"> Total Score: {{ totalScore }}</p>
    </div>

</template>