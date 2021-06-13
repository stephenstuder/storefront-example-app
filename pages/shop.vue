<template>
  <div>{{ products }}</div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      products: null,
    }
  },
  created() {
    const url = 'http://localhost:1337/products'
    axios
      .get(url)
      .then((response) => {
        this.products = response
      })
      .catch((error) => {
        console.log(error)
      })
  },
}
</script>
