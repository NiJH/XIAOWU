<template>
  <div id="app" @click.capture.stop="next">
    <template v-if="isMobile">
		<div class="body1">
	    <div class="stars" ref="starsRef">
	    	<div class="star" v-for="(item, index) in starsCount" :key="index"></div>	
	    </div>
		</div>
		<audio id="video" class = "audio_1" src="https://m3.8js.net/eu/jiu_shi_ai_ni-tao_zhe_28s.mp3" controls autoplay loop="loop"> </audio>
	    
          <FirstPage class="delay box" v-if="step === 1" @start="next"></FirstPage>
          <SecondPage class="delay box" v-if="step === 2" @click.native="next"
          ></SecondPage>
          <ThirdPage class="delay box" v-if="step === 3" @next="next"></ThirdPage>
          <ForthPage class="delay box" v-if="step === 4" @next="next"></ForthPage>
          <FifthPage class="delay box" v-if="step === 5" @next="next"></FifthPage>
          <SixthPage class="delay box" v-if="step === 6" @next="next"></SixthPage>
          <SeventhPage
            class="delay box"
            v-if="step === 7"
            @next="next"
          ></SeventhPage>
          <EighthPage class="delay box" v-if="step === 8" @next="next"></EighthPage>
	      <NinthPage class="delay box" v-if="step === 9" @next="next"></NinthPage>
	    
          <div v-if="step !== 9" class="footer"></div>
          <div :class="handleMask"></div>
        </template>
    <template v-else> 请用手机查看 </template>
  </div>
</template>

<script>
import FirstPage from "./components/FirstPage";
import SecondPage from "./components/SecondPage";
import ThirdPage from "./components/ThirdPage";
import ForthPage from "./components/ForthPage";
import FifthPage from "./components/FifthPage";
import SixthPage from "./components/SixthPage";
import SeventhPage from "./components/SeventhPage";
import EighthPage from "./components/EighthPage";
import NinthPage from "./components/NinthPage";
import sound from "./assets/images/cloud3.png";
export default {
  name: "App",
  components: {
    FirstPage,
    SecondPage,
    ThirdPage,
    ForthPage,
    FifthPage,
    SixthPage,
    SeventhPage,
    EighthPage,
    NinthPage,
  },
  data() {
    return {
      step: 1,
      mask: true,
	  sound: sound,
	  autoplay : true,
	  starsCount: 800, //星星数量
      distance: 900, //间距
    };
  },
  mounted() {
			console.log(this.$refs.starsRef.children);
			let starNodes = Array.from(this.$refs.starsRef.children);
			starNodes.forEach((item) => {
				let speed = 0.2 + Math.random() * 1;
				let thisDistance = this.distance + Math.random() * 300;
				item.style.transformOrigin = `0 0 ${thisDistance}px`;
				item.style.transform =
					`
		        translate3d(0,0,-${thisDistance}px)
		        rotateY(${Math.random() * 360}deg)
		        rotateX(${Math.random() * -50}deg)
		        scale(${speed},${speed})`;
			});
		},
  computed: {
    handleMask() {
      return {
        mask: this.mask,
      };
    },
    isMobile() {
      return (
        /AppleWebKit.*Mobile/i.test(navigator.userAgent) ||
        /MIDP|SymbianOS|NOKIA|SAMSUNG|LG|NEC|TCL|Alcatel|BIRD|DBTEL|Dopod|PHILIPS|HAIER|LENOVO|MOT-|Nokia|SonyEricsson|SIE-|Amoi|ZTE/.test(
          navigator.userAgent
        )
      );
    },
  },
  watch: {
    step() {
      this.mask = false;
      setTimeout(() => {
        this.mask = true;
      });
    },
  },
  methods: {
    next() {
      if (this.step === 9) {
        return;
      }
      this.step++;
    },
	play(){
      let vo = document.getElementById("video")
      if(this.sound == require('./assets/images/cloud3.png')){
          this.sound = require('./assets/images/cloud2.png')
          vo.autoplay = true
          vo.play()
      }
      else{
          this.sound = require('./assets/images/cloud3.png')
          vo.pause()
      }

    },
  },
};
</script>

<style>
html,
body {
  padding: 0;
  margin: 0;
  height: 100vh;
  color: white;
  overflow: hidden;
}
#app {
  background-image: linear-gradient(#1f9ef4, #a1e1ff);
  height: 100vh;
  overflow: hidden;
  font-family: "Microsoft YaHei", 微软雅黑, "Microsoft JhengHei", 华文细黑,
    STHeiti, MingLiu;
  font-size: 4vw;
}
.audio_1 {
	padding-top: 2vw;
	padding-left: 2vw;
	float:left;
	position: fixed;
	height: 8vw;
	width:65%;
}

.box {
  padding: 5vw;
  margin-top: 10vw;
  overflow: hidden;
  position: fixed;
  height : 90vh;
}
.play {
  width: 20vw;
  height: 10vh;
}
.delay {
  animation-name: delay-display;
  animation-duration: 0.5s;
  animation-delay: 0.3s;
  animation-fill-mode: backwards;
}
@keyframes delay-display {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes slide-top {
  0% {
    opacity: 0;
    transform: translateY(10vh);
  }
  100% {
    opacity: 1;
    transform: translateY(0vh);
  }
}
.value {
  display: inline-block;
  padding: 5px;
  transform: scaleY(1.1) translateY(-5.2%);
  font-weight: bolder;
  color: #ebf45f;
}
.body1 {
		position: absolute;
		width: 100%;
		height: 100%;
		margin: 0;
		padding: 0;
		background: radial-gradient(200% 100% at bottom center,
			#f7f7b6,
			#e96f92,
			#1b2947);
		background: radial-gradient(200% 105% at top center,
			#1b2947 10%,
			#75517d 40%,
			#e96f92 65%,
			#f7f7b6);
		background-attachment: fixed;
		overflow: hidden;
	}

	@keyframes rotate {
		0% {
			transform: perspective(400px) rotateZ(20deg) rotateX(-40deg) rotateY(0);
		}

		100% {
			transform: perspective(400px) rotateZ(20deg) rotateX(-40deg) rotateY(-360deg);
		}
	}

	.stars {
		transform: perspective(500px);
		transform-style: preserve-3d;
		position: absolute;
		perspective-origin: 50% 100%;
		left: 45%;
		animation: rotate 90s infinite linear;
		bottom: 0;
	}

	.star {
		width: 2px;
		height: 2px;
		background: #f7f7b6;
		position: absolute;
		left: 0;
		top: 0;
		backface-visibility: hidden;
	}
</style>
<style scoped>
.footer {
  background-image: url("~@/assets/images/foot.png");
  background-size: cover;
  width: 100vw;
  height: 20vh;
  position: absolute;
  bottom: 0vh;
  overflow: hidden;
}
.mask {
  width: 100vw;
  height: 100vh;
  z-index: -1;
  position: absolute;
  top: 0;
  animation: up-move 1s;
  background-image: url("~@/assets/images/mask.png");
  background-repeat: repeat-x;
  background-size: contain;
}
@keyframes up-move {
  0% {
    transform: translateY(0);
    z-index: -1;
  }
  100% {
    transform: translateY(-100vh);
    z-index: 2;
  }
}
</style>
