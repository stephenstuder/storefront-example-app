<template>
  <div v-if="product" class="card" @click="goToDetails">
    <img :src="imageUrl" alt="" />
    <h5 class="product-title">{{ product.title }}</h5>
    <span class="product-price">${{ product.price }}</span>
    <button
      class="snipcart-add-item"
      :data-item-id="product.title"
      :data-item-price="product.price"
      :data-item-description="product.description"
      :data-item-image="imageUrl"
      data-item-url="/shop"
      :data-item-name="product.title"
    >
      Add to cart
    </button>
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
  methods: {
    goToDetails() {
      this.$router.push(`shop/${this.product.id}`)
    },
  },
}
</script>

<style scoped>
img {
  border-radius: 10px 10px 0px 0px;
  object-fit: cover;
  width: 100%;
}
button {
  margin-bottom: 10px;
}
.card {
  width: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: all 0.2s ease-in-out;
}
.card:hover {
  transform: scale(1.1);
  cursor: pointer;
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
