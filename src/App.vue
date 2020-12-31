<template>
    <div id="app">
        <h1>Monty Hall Problem</h1>
        <Gift></Gift>
    </div> 
</template>

<script>

import Gift from './components/Gift.vue'

export default {
    name: "App",
    components: {Gift}
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
    background-color: rgba(0, 0, 0, 0.404);
}

</style>