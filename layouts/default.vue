<template>
  <div class="dark oled h-100">
    <NavBar />
    <body>
      <Nuxt />
    </body>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
export default {
  components: {
    NavBar,
  },
}
</script>

<style>
@import '@/assets/css/style.css';
@import '@/assets/css/normalize.css';
.h-100 {
  min-height: 100vh;
}
</style>
