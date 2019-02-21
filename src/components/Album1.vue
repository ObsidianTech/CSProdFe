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
              <player/>
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
            <a href="https://www.facebook.com/Crypt0Sound/"><img class="social" src="../assets/icons/Facebook.svg" /></a>
            <a href="https://www.instagram.com/crypto_sound/?hl=en"><img class="social" src="../assets/icons/Instagram.svg" /></a>
            <a href="https://twitter.com/nameschrisjames"><img class="social" src="../assets/icons/Twitter.svg" /></a>
            <a href="https://www.youtube.com/channel/UC_0j0BlEHk3vvFFy6JmE34g/featured"><img class="social" src="../assets/icons/YouTube.svg" /></a>
          </div>
        </div>
  </div>
</template>

<script>
import player from './player'
    export default {
  name: "Album1",
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
  width: 100%;
  left:0; right:0;
  top:0; bottom:0;
  margin:auto;
  display: inline-block;
}

.footericons{
  display: flex;
  height: 100%;
  padding: 0;
  margin: 0;
  align-items: center;
  justify-content: center;
}

.social{
  flex: 25%;
  width: 85%;
  height: auto;
  margin: 0 5% 0 5%;
}

@media only screen and (min-width:474px) {
    .banner{
      width:100%;
      height: auto; 
      align-items: center;
      justify-content: center;
    }

    .banner img{
      display: block;
      height:90px;
      width:auto;
      margin-left: auto;
      margin-right: auto;
    }

    .covercontainer img{
    width: 65%;
    height: auto;
    }

    .arrow{
      display: none;
    }

    .arrow::before{
      display: none;
    }
}

@media only screen and (min-width:587px) {
  .covercontainer img{
    padding:13px;
    width: 350px;
    height: auto;
    }
}
</style>
