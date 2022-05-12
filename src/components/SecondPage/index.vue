<template>
  <div>
    <div class="a">这是我们在一起的第一年</div>
    <div class="b">愿年年有我，岁岁有你</div>
    <div class="c">一起去看看我们的这一年吧~</div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.a,
.b,
.c {
  text-align: center;
  color: white;
}
.a {
  font-size: 8vw;
  padding-top: 15vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: .5s;
  animation-fill-mode: backwards;
}
.b {
  font-size: 6vw;
  padding-top: 15vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.c {
  font-size: 6vw;
  padding-top: 5vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1.5s;
  animation-fill-mode: backwards;
}
</style>