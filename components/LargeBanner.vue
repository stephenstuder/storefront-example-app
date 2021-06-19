<template>
  <div class="large-banner">
    <img src="~/assets/images/podcast.jpg" alt="podcast studio" />
    <div class="large-banner-text">
      <span
        >BRINGING YOU ALL THE NEWS THAT ONLY A FAKE PORTFOLIO PROJECT CAN</span
      >
      <h1>FAKE MOTOCROSS PODCAST</h1>
      <NuxtLink to="/shop">
        <button class="large">BUY MERCH</button>
      </NuxtLink>
    </div>
  </div>
</template>

<style scoped>
.large-banner {
  width: 100%;
  height: 100%;
  object-fit: cover;
  margin: 0;
  position: relative;
  display: grid;
  place-items: center;
}
.large-banner-text {
  position: absolute;
  margin: 10px;
}
.large-banner-text h1 {
  background: var(--darkGrey);
}
.large-banner-text span {
  background: black;
  color: white;
}
img {
  border-radius: 0;
  width: 100%;
  min-height: 100vh;
  object-fit: cover;
}
</style>
