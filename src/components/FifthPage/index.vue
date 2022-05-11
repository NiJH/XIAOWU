<template>
  <div>
    <div class="a">
      这一年 我们说过最晚的一句话
      <br />
      在凌晨
      <span class="value">
        {{ hour }}
      </span>
      点
    </div>
    <div class="b">
      <span style="font-size: 4vw"> {{ user }}: </span>
      {{ content }}
    </div>
    <div class="c">...</div>
    <div class="d">
      {{ time }}
    </div>

    <div class="e" style="padding-top: 5vh; font-size: 4vw">你看，那晚你也胃疼，一直到四点多才昏昏沉沉的睡了。以后我们都要按时吃饭，好好养胃，不许再有胃不舒服咯，不然冰淇淋要没得吃的。</div>
  </div>
</template>

<script>
import { latestMsg } from "@/data.json";
export default {
  data() {
    return {
      ...latestMsg,
    };
  },
};
</script>

<style scoped>
.a {
  font-size: 5vw;
  padding-top: 15vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 0.5s;
  animation-fill-mode: backwards;
}
.b {
  padding-top: 5vh;
  white-space: normal;
  text-overflow: ellipsis;
  overflow: hidden;
  line-height: 2;
  color: ebf45f;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.c {
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1.5s;
  animation-fill-mode: backwards;
}
.d {
  text-align: right;
  padding-top: 3vh;
  font-weight: bolder;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 2s;
  animation-fill-mode: backwards;
}
.e{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 2.5s;
  animation-fill-mode: backwards;
}
</style>