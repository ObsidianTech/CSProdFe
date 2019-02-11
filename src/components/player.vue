<template>
    <div>
        <button v-on:click="play"></button>
    </div>
</template>

<script>
var song = new Audio('../assets/tracks/5G.mp3');
export default{
    name: "player",
    methods:{
        play: function (){
            song.play();
        }
    }
}
</script>

<style scoped>
button{
    width:30px;
    height:30px; 
    background-color: white;
}
</style>
