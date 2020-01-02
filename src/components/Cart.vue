<template >
  <div>
    <ul class="list-group">
      <li class="list-group-item" v-for="item in items" :key="item.id">
        {{ item.titulo }} - {{ item.precio }}
        <button type="button" name="delete"
          class="btn badge badge-danger float-right" @click="removeItem(item)">
          Eliminar
        </button>
      </li>
    </ul>
    <!-- Ends cart items -->
    <div class="card p-3 my-5">
      <h4 class="text-center">Total: ${{ total }}</h4>
    </div>
    <!-- Ends total -->
    <button type="button" name="pay" class="btn btn-info form-control"
      @click="$emit('payment')" :disabled="items.length === 0">
      Pagar Ahora
    </button>
  </div>
</template>

<script>
  export default{
    name: 'Cart',
    props: ['items'],
    computed: {
      total(){
        return this.items.reduce(
          (acumulador, item) => acumulador + Number(item.precio), 0
        );
      }
    },
    methods: {
      removeItem(item){
        this.$emit('remove-item', item)
      }
    }
  }
</script>
