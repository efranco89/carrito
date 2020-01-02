<template>
  <div id="app">
    <div class="row">
      <div class="col-md-7">
        <div class="row">
          <div class="col-md-6">
            <product/>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
  import Product from './components/Product.vue'
  export default {
    name: 'app',
    components: {
      Product
    }
  }
</script>

<style>

</style>
