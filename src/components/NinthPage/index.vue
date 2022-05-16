<template>
	
    <div class="a">
	<div class="a1">
      <div class="b">#一周年</div>
      <div class="c">年度聊天报告</div>
      <div class="d">关键词</div>
      <div class="e">吃</div>
      <div class="f"></div>
      <div class="d">爱意词</div>
      <div class="e">想你</div>
      <div class="f"></div>
      <div class="d">话痨月</div>
      <div class="e" style="font-size: 5vw">12月</div>
      <div class="f"></div>
      <div class="h">
        <img class="p" src="@/assets/images/result2.png" />
        <img class="y" src="@/assets/images/cloud2.png" />
      </div>
      <div class="j">我们要</div>
      <div class="i">一直热恋</div>
	  </div>
    </div>

</template>

<script>
import data from "@/data.json";
export default {
  data() {
    const { loveWord, mostWord, monthGroup } = data;
    let max = monthGroup[0];
    for (let i of monthGroup) {
      if (i[1] > max[1]) {
        max = i;
      }
    }
    let lc = {
      w: "",
      c: 0,
    };
    Object.keys(loveWord).forEach((key) => {
      const count = loveWord[key];
      if (count > lc.c) {
        lc = {
          w: key,
          c: count,
        };
      }
    });

    let mc = {
      w: "",
      c: 0,
    };

    Object.keys(mostWord).forEach((key) => {
      const count = mostWord[key];
      if (count > mc.c) {
        mc = {
          w: key,
          c: count,
        };
      }
    });
    return {
      a: mc.w,
      b: lc.w,
      c: max[0],
    };
  },
};
</script>

<style scoped>
.v {
  background-image: linear-gradient(#f89d92, #fac9bf);
  height: 100%;
  color: #73e373;
}
.a {
  margin-top: 15vh;
  height: 60vh;
  //background-color: unset;
  //border: 5px #1B2947 solid;
  
  padding: 3vw;
  width: 94vw;
  
}
.a1{
	background: #fef9f9;
	opacity: 0.85;
	height: 100vh;
	padding: 3vw;
}
.b {
  font-size: 13vw;
  padding-bottom: unset;
  color: #73e373;
}
.c {
  font-size: 5vw;
  font-weight: 700;
  padding-bottom: 5vh;
  color: #73e373;
}
.d {
  color: black;
  font-weight: bold;
}
.e {
  color: black;
  /* font-weight: bold; */
  font-size: 12vw;
}
.f {
  height: 1px;
  background: #73e373;
  width: 30vw;
  margin-top: 2vh;
  margin-bottom: 2vh;
}
.p {
  position: absolute;
  width: 47vw;
  left: 43vw;
  top: 30vh;
  z-index: 2;
}
.y {
  position: absolute;
  width: 60vw;
  left: 36vw;
  top: 40vh;
}
.i,
.j {
  position: absolute;
  color: #3c4739;
}
.j {
  font-size: 10vw;
  top: 15vh;
  left: 50vw;
}
.i {
  font-size: 10vw;
  top: 23vh;
  left: 55vw;
}
</style>