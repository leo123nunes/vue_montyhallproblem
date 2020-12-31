<template>
    <div class="gift">
        <div class="gift-top"></div>
        <div class="gift-tape1"></div>
        <div class="gift-tape2"></div>
        <div class="gift-body"></div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style>
.gift{
    display: flex;
    flex-direction: column;
    align-items: center;
}

.gift-top{
    height: 20px;
    width: 70px;
    background-color: #13991e;
}

.gift-tape1{
    width: 60px;
    height: 10px;
    position: absolute;
    background-color: red;
    margin-top: 35px;
}

.gift-tape2{
    width: 10px;
    height:70px;
    position: absolute;
    background-color: red;
    margin-left: 0px;
}

.gift-body{
    width: 60px;
    height: 50px;
    background-color: #0a5810;
}
</style>