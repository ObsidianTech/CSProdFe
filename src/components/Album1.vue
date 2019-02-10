<template>
    <div container>
        <div class="header"><p>C R Y P T O S O U N D</p></div>
        <div class=banner>
            <img src="../assets/CryptoLogo2.svg"/>
        </div>
        <div class="albumcontainer">
          <div class="covercontainer"><img src="../assets/TIADCover(Final).png"/></div>
          <div class="arrow"></div>
          <div class="tracklistcontainer">
            <table class="tracklist">
              <tr class="track" v-for="track in tracks" :key="track.file"  style="padding: 20px;">
                <td>
                  <player :name="track.name" :file="track.file" />
                </td>
              </tr>
            </table>
          </div>
        </div>
        <div class="bio">
          <p>
            Social Media. Amazon. Porn. Trolling.
            Have you ever taken the time to ask yourself 
            "What are these things doing to my mind, my body"?
            A drug is classified as any substance that causes physiological 
            change in your body. 
            
            <br/><br/> Sound familiar? 
          </p>
        </div>
        <div class="footer">
          <div class="footericons">
            <img src="../assets/icons/Facebook.svg" />
            <img src="../assets/icons/Instagram.svg" />
            <img src="../assets/icons/Twitter.svg" />
          </div>
        </div>
  </div>
</template>

<script>
import player from './player'
    export default {
  name: "Album1",
  data() {
    return {
      tracks: [
        {
          name: '5G',
          file: '../assets/tracks/5G.mp3'
        }
      ]
    }
  },
  components:{
    player
  }
};
</script>

<style scoped>
.albumcontainer {
  position: relative;
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  min-height: 100%;
  height: 100%;
  width: auto;
  background-attachment: fixed;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.tracklistcontainer {
  margin: 15px;
}

.covercontainer {
  margin-top:25px;
  margin-left: auto;
  margin-right: auto;
}
.covercontainer img{
    width: 95%;
    height: auto;
}

.tracklist {
  margin-left: auto;
  margin-right: auto;
}
.header{
    text-align: center;
}

table {
  border-collapse: collapse;
  padding: 20px;
}

.track {
  text-align: center;
  align-items: center;
  justify-content: center;
  margin-left: auto;
  margin-right: auto;
  border: 2px solid white;
}

.arrow{
    margin:18%;
}

.arrow::before{
    content: '╲╱';
    color: #fff;
    font-size: 20px;
    width: 60px;
    height: 40px;
    line-height: 40px;
    text-align: center;
    border-radius: 10px;
    bottom: 20px;
    left: 50%;
    margin-left: auto;
    margin-right: auto;
    animation: bounce 1s ease infinite;
}

@keyframes bounce {
  50% {
    transform: translateY(-50%);
  }
  100% {
    transform: translateY(0);
  }
}

@-moz-keyframes bounce {
  50% {
    transform: translateY(-50%);
  }
  100% {
    transform: translateY(0);
  }
}

@-webkit-keyframes bounce {
  50% {
    transform: translateY(-50%);
  }
  100% {
    transform: translateY(0);
  }
}

@-o-keyframes bounce {
  50% {
    transform: translateY(-50%);
  }
  100% {
    transform: translateY(0);
  }
}

.container {
  min-height: 100%;
  height: 100%;
}

.bio{
    text-align: center;
    margin:8%;
}

.footer{
  height: 100px;
  left:0; right:0;
  top:0; bottom:0;
  margin:auto;
  display: inline-block;
}

.footericons{
  display: flex;
}

.footer img{
  flex: 30%;
  width: 20%;
  height: auto;
  margin: 0 5% 0 5%;
}
</style>
