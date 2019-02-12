<template>
    <div class="playerbox">
        <div>
            <button v-on:click="previousTrack()">{{ pre }}</button>
        </div>
        <div>
            <button v-on:click="play(); changeState();">{{ state }}</button>
        </div>
        <div>
            <button v-on:click="nextTrack()">{{ next }}</button>
        </div>
    </div>
</template>

<script>
var songs = ["5G.mp3", "2.VPN2.mp3"]
var currentSong = 0;
var song = new Audio();

export default{
    name: "player",
    data(){
        return{
            isPlaying: false,
            state: "|>",
            pre: "<",
            next: ">"
        }
    },
    methods:{
        play: function (){
            if(song.paused){
                if(song.currentTime == 0){
                    song.src = require("../assets/tracks/" + songs[currentSong]);
                }
                song.play();
            }else{
                song.pause();
            }
        },
        changeState: function (){
            this.isPlaying = !this.isPlaying;
            this.state = this.isPlaying ? '||':'|>'
        },
        nextTrack: function (){
            currentSong++;

            if(currentSong == songs.length){
                currentSong = 0;
            }
            song.src = require("../assets/tracks/" + songs[currentSong]);
            song.play();
            this.isPlaying = true;
            this.state = this.isPlaying ? '||':'|>'
        },
        previousTrack: function (){
            if(currentSong == 0){
                currentSong = songs.length - 1;
            }else{
                currentSong--;
            }
            song.src = require("../assets/tracks/" + songs[currentSong]);
            song.play();
            this.isPlaying = true;
            this.state = this.isPlaying ? '||':'|>'
        }
    }
}
</script>

<style scoped>
button{
    width:auto;
    height:70px;
    color:blanchedalmond;
    font-size: 2em;
    text-align:center;
    justify-content: center;
    align-items: center;
}

.playerbox{
    display:flex;
}

.playerbox div{
    flex: 33%;
    margin: 20px;
    padding: 5px;
}
</style>
