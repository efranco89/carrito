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
  </div>
</template>

<script>
  export default{
    name: 'Cart',
    props: ['items'],
    methods: {
      removeItem(item){
        this.$emit('remove-item', item)
      }
    }
  }
</script>
