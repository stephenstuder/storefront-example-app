<template>
  <header>
    <nav>
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/shop">Shop</NuxtLink>
      <NuxtLink to="/about">About</NuxtLink>
      <div class="cart">
        <a href="https://facebook.com" target="_blank">
          <facebook-icon size="1.5x" class="icon"></facebook-icon>
        </a>
        <a href="https://instagram.com" target="_blank">
          <instagram-icon class="icon"></instagram-icon>
        </a>
        <a href="#">
          <shopping-cart-icon class="snipcart-checkout"></shopping-cart-icon>
        </a>
      </div>
    </nav>
  </header>
</template>

<script>
import {
  FacebookIcon,
  InstagramIcon,
  ShoppingCartIcon,
} from 'vue-feather-icons'

export default {
  components: {
    FacebookIcon,
    InstagramIcon,
    ShoppingCartIcon,
  },
}
</script>

<style scoped>
.cart {
  float: right;
  display: flex;
  justify-content: center;
  align-items: center;
}
.cart:hover {
  cursor: pointer;
  scale: 1.5;
}
.icon {
  margin-right: 10px;
}
nav {
  width: 100%;
}
</style>
