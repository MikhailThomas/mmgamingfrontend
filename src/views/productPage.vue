<template>
<section id="page" class="container">
  <div v-if="singleProduct" id="info" class="row my-5 py-3">
    <div class="col-md-6">
      <img id="product" :src="singleProduct[0].img" alt="">
    </div>
    <div class="col-md-6">
      <h1>{{ singleProduct[0].title}}</h1>
      <h2>{{singleProduct[0].genre}}</h2>
      <p>{{singleProduct[0].description}}</p>
      <h2>Price:R{{ singleProduct[0].price }}</h2>
      <h2>Quantity:{{singleProduct[0].quantity}}</h2>
      <bag/>
    </div>
    <div id="preview">
    </div>
  </div>
  <div v-else>
<h2>
  Loading ...
</h2>
  </div>
</section>
</template>

<script>
import bag from '../components/bag.vue'

export default {
  components: {
    bag
  },
  computed:{
      singleProduct(){
        return this.$store.state.product
      }
    },
  mounted(){
    this.$store.dispatch('fetchSingleProduct', this.$route.params.id)
  },
} 

</script>

<style scoped>
#info{
  margin: auto;
  background-color: rgba(255, 255, 255, 0.507);
  max-width: 600px;
}
</style>
