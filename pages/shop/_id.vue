<template>
  <div v-if="product" class="layout product-details">
    <arrow-left-circle-icon
      size="1.5x"
      class="back float-left"
      @click="back"
    ></arrow-left-circle-icon>
    <h2>{{ product.data.title }}</h2>
    <img :src="imageUrl" alt="productImage" />
  </div>
</template>

<script>
import { ArrowLeftCircleIcon } from 'vue-feather-icons'

import axios from 'axios'
export default {
  components: {
    ArrowLeftCircleIcon,
  },
  data() {
    return {
      product: null,
      url: null,
    }
  },
  computed: {
    imageUrl() {
      return this.url + this.product.data.image[0].url
    },
  },
  created() {
    this.url = 'http://localhost:1337'
    axios
      .get(this.url + `/products/${this.$route.params.id}`)
      .then((response) => {
        this.product = response
      })
      .catch((error) => {
        console.log(error)
      })
  },
  methods: {
    back() {
      this.$router.go(-1)
    },
  },
}
</script>

<style scoped>
.back {
  transition: all 0.2s ease-in-out;
  display: flex;
}
.back:hover {
  cursor: pointer;
  transform: scale(1.1);
}
.product-details {
  display: flex;
  flex-direction: column;
}
.float-left {
  align-self: start;
}
</style>
