<template>
  <div v-for="phone in books" :key="phone.id">
    <SingleBook :phone="phone" />
  </div>
</template>

<script>
import SingleBook from './SingleBook.vue'

export default {
  name: 'BookBox',
  props: {
    books: Array
  },
  components: {
    SingleBook
  }
}
</script>

<style scoped>
div {
  text-align: center;
  margin-bottom: 1em;
}
</style>
