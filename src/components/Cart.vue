<template >
  <div>
    <ul class="list-group">
      <li class="list-group-item" v-for="item in items" :key="item.id">
        {{ item.titulo }} - {{ item.precio }}
      </li>
    </ul>
  </div>
</template>

<script>
  export default{
    name: 'Cart',
    props: ['items']
  }
</script>
