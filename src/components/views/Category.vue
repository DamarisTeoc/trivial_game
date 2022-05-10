<script setup>

import axios from 'axios';

axios.get("https://opentdb.com/api.php?amount=4")

</script>

<template>
    <img class="img" src="src\components\icons\question.png" alt="">
    <h1 class="title">This is an a question in the game?</h1>
    <button  class="Question" input="Hola">Rey de roma
        <span class="button__text"></span>
        <span class="button--   "></span>
        <ion-icon name="chevron-forward-outline"></ion-icon>
    </button>
    <button class="Question2">Pregunta 2</button>
    <button class="Question 3">Question 3</Button>
    <button class="Question 1">Question 4</button>



</template>

<style scoped>

.title{
    margin-bottom:50px;
    display: flex;
    justify-content: center;
}

.Question {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    font-size: 1.5em;
    font-weight: 300;
    color: black;
    padding: 10px;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #000;
    margin-bottom: 40px;
    font-family: 'JetBrains Mono', monospace;
}

.Question2 {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    font-size: 1.5em;
    font-weight: 300;
    color: black;

    padding: 10px;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #000;
    margin-bottom: 40px;
    font-family: 'JetBrains Mono', monospace;
}

.Question3 {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    font-size: 1.5em;
    font-weight: 300;
    color: #fff;
    padding: 10px;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #000;
    margin-bottom: 40px;
    font-family: 'JetBrains Mono', monospace;
}

.Question4 {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    font-size: 1.5em;
    font-weight: 300;
    color: #fff;
    padding: 10px;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #000;
    font-family: 'JetBrains Mono', monospace;   
}

.img{
    display: flex;
    align-content: center;
}




</style>
