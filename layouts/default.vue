<template>
  <div>
    <NavBar />
    <body>
      <Nuxt class="layout" />
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
</style>
