<template>
    <div>
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
            <p>{{trackname}}</p>
    </div>
</template>

<script>
var songs = ["5G.mp3","2. vpn.mp3","3 a.m..mp3","Amazon Prime.mp3","OMW.mp3","Peach Emoji (Interlude).mp3","Torrents.mp3","Relapse.mp3","Withdrawal.mp3","Sober.mp3","A New Day.mp3"];
var tracknames = ["5G","vpn","3 a.m.","Amazon Prime","OMW","Peach Emoji (Interlude)","Torrents","Relapse","Withdrawal","Sober","A New Day"]
var currentSong = 0;
var song = new Audio();
export default{
    name: "player",
    data(){
        return{
            isPlaying: false,
            state: "|>",
            pre: "<",
            next: ">",
            percentage: 0,
            trackname: undefined
        }
    },
    methods:{
        setPosition: function(val) {
            this.song.currentTime = parseInt(this.song.duration * (val/100));
        },
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
            this.setTitle();
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
            this.setTitle();
        },
        track: function(){
            this.percentage = song.currentTime / song.duration * 100;
        },
        setTitle: function (){
            this.trackname = tracknames[currentSong];
        },
        init: function(){
            song.addEventListener("timeupdate", this.track);
            song.addEventListener("ended", this.nextTrack);
            this.setTitle();
        }
    },
    mounted() {
        this.init();
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
    background-color:black;
    border: none;
}

.playerbox{
    display:flex;
}

.playerbox div{
    flex: 33%;
    margin: 20px;
    padding: 5px;
}

.seek{
    width:250px;
    height:5px;
    background-color: antiquewhite;
    display: flex;
    border-radius: 50px;
    margin-left:auto;
    margin-right:auto;
}

.fill{
    height: 5px;
    background-color: black;
    border-radius: 20px;
}

.handle{
    height:8px;
    width:8px;
    background-color: lightgray;
    border-radius: 50%;
    margin-left:-5px;
    transform:scale(2);
}

.tracking{
    height: 25px;
    width: auto;
    border: 2px solid white;
}

.seek{
    -webkit-appearance: none;
    border: 1px solid black;
    top: 18px;
    display: block;
    width: 100%;
    height: 15px;
 
    -webkit-border-radius: 20px;
    -moz-border-radius: 20px;
    border-radius: 20px;
    background-color: lightgray;
    margin:0 auto;
 
    -webkit-box-shadow: inset 0px 4px 4px rgba(0,0,0,.6);
    -moz-box-shadow: inset 0px 4px 4px rgba(0,0,0,.6);
    box-shadow: inset 0px 4px 4px rgba(0,0,0,.6);
}

.seek::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 20px;
    height: 20px;
    border:1px solid black;
 
    -webkit-border-radius: 10px;
    border-radius: 10px;
    background: blanchedalmond; /* Old browsers */
    /*background: -webkit-linear-gradient(top, #80e4df 0%, #75dbd6 13%, #5ec4bf 33%, #57bbb6 47%, #419d99 80%, #378f8b 100%);
 
    background: -moz-linear-gradient(top, #80e4df 0%, #75dbd6 13%, #5ec4bf 33%, #57bbb6 47%, #419d99 80%, #378f8b 100%);
    background: -o-linear-gradient(top, #80e4df 0%, #75dbd6 13%, #5ec4bf 33%, #57bbb6 47%, #419d99 80%, #378f8b 100%);
    background: linear-gradient(top, #80e4df 0%, #75dbd6 13%, #5ec4bf 33%, #57bbb6 47%, #419d99 80%, #378f8b 100%);*/
}

@media only screen and (min-width:474px) {
    .playerbox div{
        flex: 33%;
        margin: 45px;
        padding: 5px;
    }
}

</style>