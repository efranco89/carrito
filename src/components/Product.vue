<template>

  <div class="card my-5">
    <div class="card-body">
      <h5 class="text-center card-title">{{ product.titulo }}</h5>
      <img :src="product.imagen" alt="" width="260" height="150">
      <p class="text-center text-muted card-text display-4">$ {{ Number(product.precio).toFixed() }}</p>
      <button type="button" name="add" class="btn btn-primary form-control"
      @click="addToCart(product)" :disabled="isOnCart">
        {{ isOnCart ? 'Agregado' : 'Agregar' }}
      </button>
    </div>
  </div>

</template>

<script>
  export default{
    name: 'Product',
    props: ['product', 'isOnCart'],
    methods: {
      addToCart(product){
        this.$emit('add-cart', product);
      }
    }
  }
</script>

<style>

</style>
