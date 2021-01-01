<template>
    <div id="app">
        <h1>Monty Hall Problem</h1>
        <div class="form" v-if="!start">
            <div class="firstQuestion">
                <label>How many doors?</label>
                <input v-model="numberDoors" type="text" size="1">
            </div>

            <div class="secondQuestion">
                <label>Wich door is awarded?</label>
                <input v-model="numberGift" type="text" size="1">  
            </div>
            
            <div class="buttonArea">
                <button v-on:click="start = !start" class="buttonStart">Start</button>
            </div>
        </div>

        <div v-if="start" class="running">
            <div class="buttonRestartArea">
                <button v-on:click="start = !start" class="buttonRestart">Restart</button><br>
            </div>
            
            <div class="doorsArea">
                <div v-for="index in parseInt(numberDoors)" :key="index">
                    <Door :number="index" :isGift="numberGift == index"></Door> 
                </div> 
            </div>
        </div>
    </div> 
</template>

<script>

import Door from './components/Door.vue'

export default {
    name: "App",
    components: {Door},
    data: function(){
        return {
            start: false,
            numberDoors: null,
            numberGift: null
        }
    }
}
</script>

<style>
*{
    font-family: "Montserrat";
}

body{
    background: rgba(0, 0, 0, 0) linear-gradient(to right, rgb(40, 60, 134), rgb(69, 162, 71)) repeat scroll 0% 0%;
    color: #fff;
}

#app{
    display: flex;
    flex-direction: column;
    align-items: center;
}

#app h1{
    padding: 20px;
    border: solid 1px rgb(0, 0, 0);
    background-color: rgba(0, 0, 0, 0.267);
}

.form label, .form input, .form button, .buttonRestart{
    font-size: 1.5rem;
    margin: 10px;
}

.firstQuestion{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.secondQuestion{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.buttonArea{
    display: flex;
    justify-content: center;
    align-items: center;
}

.buttonStart{
    width: max-content;
}

.form{
    margin-top: 40px;
    display: flex;
    flex-direction: column;
}

.running{
    display: flex;
    flex-direction: column;
    width: 100%;
}

.doorsArea{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    flex-wrap: wrap;
}

.buttonRestartArea{
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>