<template>
  <div v-if="products" class="layout">
    <h2>Shop</h2>
    <div class="product-list">
      <ProductCard
        v-for="product in products.data"
        :key="product.id"
        :product="product"
      />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import ProductCard from '@/components/ProductCard.vue'
export default {
  components: {
    ProductCard,
  },
  data() {
    return {
      products: null,
      url: null,
    }
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
.product-list {
  display: flex;
  flex-wrap: wrap;
}
</style>
