<template>
  <div class = "a1">
    <div class="a">遇到你是我最大的幸运</div>
 <div class="b">
      <img src="@/assets/images/girl.jpg" />
    </div>
  </div>

</template>

<script>
export default {};
</script>

<style scoped>
.a1 {
  text-align: center;
  color: white;
  padding: 0;
}
.a {
  width:100vw;
  font-size: 8vw;
  padding-top: 15vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.b {
 opacity: 0.85;
  width: 100%;
  margin-top: 5vh;
  animation-name: slide-top;
  animation-duration: 2s;
  animation-delay: 2s;
  animation-fill-mode: backwards;
}
.b img {
    width: 80vw;
}
</style>