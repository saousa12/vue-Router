<template>
  <div class="container">
    <p class="text">Welcome to my WebSite</p>
  </div>
</template>

<script>
export default {};
</script>

<style>
.container {
  display: inline-block;
  margin: 20%;
}
.text {
  overflow: hidden;
  font-size: 3.6rem;
  font-weight: 700;
  border-right: 0.15rem solid orange;
  white-space: nowrap;
  animation: typing 4s steps(40, end);
}

@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}
</style>
