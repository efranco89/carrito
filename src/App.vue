<template>
  <div id="app" class="container">
    <div class="row">
      <div class="col-md-7">
        <div class="row">
          <div class="col-md-6" v-for="prod in products" :key="prod.id">
            <product :product="prod" v-on:add-cart="addItemToCart" :isOnCart="isOnCart(prod)"/>
          </div>
        </div>
      </div>
      <!-- Ends products -->
      <div class="col-md-5 my-5">
        <cart :items="cart" v-on:remove-item="removeProduct" v-on:payment="doPayment"/>
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
      },
      isOnCart(product){
        const item = this.cart.find(item => item.id === product.id);
        if (item) {
          return true
        }else {
          return false
        }
      },
      removeProduct(product){
        this.cart = this.cart.filter(item => item.id != product.id);
      },
      doPayment(){
        this.cart = [];
        alert('Venta completada');
      }
    }
  }
</script>

<style>

</style>
