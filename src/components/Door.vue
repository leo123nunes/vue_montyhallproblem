<template>
    <div class="door-area">
        <div class="door-frame" :class="{selected, openDoor}" v-on:click="selected = !selected && !openDoor">
            <div class="door-number" :class="{selected, openDoor}">{{number}}</div>
            <div class="knob" :class="{selected, openDoor}" v-on:click="openDoor = !openDoor"></div>
        </div>
        <Gift id="gift" v-if="isGift"></Gift>
    </div>
</template>

<script>
import Gift from './Gift.vue'

export default {
    name: "Door",
    components: {Gift},
    data: 
        function(){
            return {
                openDoor: false,
                selected: false
            }
    },
    props: {
        isGift: { Boolean },
        number: {}
    }
}
</script>

<style>
:root{
    --color-border: 5px solid brown;
    --color-border-selected: 5px solid #cfd306;
    --color-selected: #cfd306;
}

*{
    font-family: "Montserrat";
    font-weight: bolder;
}

.door-area{
    display: flex;
    flex-direction: column;
    justify-content: end;
    align-items: center;
    width: 180px;
    height:280px;
    border-bottom:10px solid rgb(180, 180, 180);
    margin-bottom: 80px;
    margin: 40px;
}

.door-frame{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 150px;
    height: 300px;
    background-color: rgb(182, 93, 51);
    border-left: var(--color-border);
    border-top: var(--color-border);
    border-right: var(--color-border);
    font-size: 2em;
    z-index: 2;
}

.knob{
    width: 20px;
    height: 20px;
    border-radius: 20px;
    background-color: brown;
    align-self: flex-start;
    margin-left: 10px;
    margin-top: 100px;
}

.door-number{
    margin-top: 20px;
}

#gift{
    position: absolute;
    z-index: 1;
}

.door-frame.selected{
    border-left: var(--color-border-selected);
    border-top: var(--color-border-selected);
    border-right: var(--color-border-selected);
}

.door-number.selected{
    color: var(--color-selected);
}

.knob.selected{
    background-color: var(--color-selected);
}

.door-frame.openDoor{
    background-color: rgba(37, 93, 59, 0.534);
    z-index: 0;
    /* background-color: rgba(28, 66, 43, 0); */
}

.knob.openDoor{
    display: none;
}

.door-number.openDoor{
    display: none;
}
</style>