<template>
  <div>
    <div v-if="products" class="card">
      <img :src="imageUrl" alt="" />
      <h3>{{ products.data[0].title }}</h3>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      products: null,
      url: null,
    }
  },
  computed: {
    imageUrl() {
      return this.url + this.products.data[0].image[0].url
    },
  },
  created() {
    this.url = 'http://localhost:1337'
    axios
      .get(this.url + '/products')
      .then((response) => {
        this.products = response
      })
      .catch((error) => {
        console.log(error)
      })
  },
}
</script>
<style scoped>
img {
  border-radius: 0;
  object-fit: cover;
}
</style>
