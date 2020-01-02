<template>
  <div id="app" class="container">
    <div class="row">
      <div class="col-md-7">
        <div class="row">
          <div class="col-md-6" v-for="prod in products" :key="prod.id">
            <product :product="prod" v-on:add-cart="addItemToCart"/>
          </div>
        </div>
      </div>
      <!-- Ends products -->
      <div class="col-md-5 my-5">
        <cart :items="cart"/>
      </div>

    </div>
  </div>
</template>

<script>
  import products from './productos.json'
  import Product from './components/Product.vue'
  import Cart from './components/Cart.vue'
  export default {
    name: 'app',
    components: {
      Product,
      Cart
    },
    data(){
      return {
        products,
        cart: []
      }
    },
    methods: {
      addItemToCart(product){
        this.cart.push(product);
      }
    }
  }
</script>

<style>

</style>
