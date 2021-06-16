<template>
  <div v-if="product" class="card">
    <img :src="imageUrl" alt="" />
    <h5 class="product-title">{{ product.title }}</h5>
    <span class="product-price">${{ product.price }}</span>
  </div>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      default: () => {},
    },
  },
  data() {
    return {
      url: null,
    }
  },
  computed: {
    imageUrl() {
      return this.url + this.product.image[0].url
    },
  },
  created() {
    this.url = 'http://localhost:1337'
  },
}
</script>

<style scoped>
img {
  border-radius: 10px 10px 0px 0px;
  object-fit: cover;
  width: 100%;
}
.card {
  width: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.product-title {
  margin-top: 10px;
}
.product-price {
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 10px;
}
</style>
