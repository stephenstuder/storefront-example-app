<template>
  <div v-if="product" class="layout">
    <arrow-left-circle-icon
      size="1.5x"
      class="custom-class"
    ></arrow-left-circle-icon>

    {{ product }}
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
}
</script>
