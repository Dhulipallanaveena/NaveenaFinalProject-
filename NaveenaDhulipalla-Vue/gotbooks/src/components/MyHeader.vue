<template>

    <h1>{{ bookName }}</h1>
    <h3>{{ authorName }}</h3>
</template>

<script>

export default {
  name: 'MyHeader',
  props: {
    bookName: String,
    authorName: String
  }
}

</script>


<style scoped>

div{
    text-align: center;
}

</style>