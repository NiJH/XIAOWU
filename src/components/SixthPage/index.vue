<template>
  <div>
    <div style="padding-top: 15vh" class="a">
      这一年 我们说过最多的词是

      <span style="font-size: 5vw" class="value"> {{ content }} </span>
      居然有
      <span class="value"> {{ count }}</span>
	  次，看来我们都是活在当下的人
    </div>
	<div class="b1">
    <div class="b">
      <img src="@/assets/images/cy2.png" />
    </div>
	</div>
  </div>
</template>

<script>
import { mostWord } from "@/data.json";
export default {
  data() {
    return {
      ...mostWord,
    };
  },
};
</script>

<style scoped>
.a{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 0.5s;
  animation-fill-mode: backwards;
}
.b1 {
  width: 100%;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.b img {
  width: 100%;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
  animation: hvr-ripple-out 2s ease-in-out infinite alternate both;
}
@keyframes hvr-ripple-out {
  100% {
    transform: scale(1.05);
  }
}
</style>