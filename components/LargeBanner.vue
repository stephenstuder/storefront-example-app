<template>
  <div class="large-banner">
    <img src="https://via.placeholder.com/1500" alt="placeholder image" />
    <div class="large-banner-text">
      <span>SHERCO, REIJU, ELECTRIC MOTION, SWM, GASGAS LEGACY</span>
      <h1>DIRTBIKE SPECIALISTS</h1>
      <button class="large">SHOP NOW</button>
    </div>
  </div>
</template>

<style scoped>
.large-banner {
  width: 100%;
  height: 80vh;
  border: 1px solid green;
  margin: 0;
  position: relative;
  display: grid;
  place-items: center;
}
.large-banner-text {
  position: absolute;
}
.large-banner-text h1 {
  background: white;
}
.large-banner-text span {
  background: black;
  color: white;
}
img {
  border-radius: 0;
  width: 100%;
  height: 100%;
}
</style>
