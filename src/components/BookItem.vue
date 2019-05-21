<template>
  <li><strong>{{book.title}}:</strong> {{book.author}} <a class="delete" v-on:click.prevent="bookDelete(book)">x</a></li>
</template>

<script>
  export default {
    name: "BookItem",
    props: ["book"],
    methods: {
      bookDelete(book) {
        this.$emit('deleteBook', book);
      },
    },
  };
</script>

<style scoped>
  li {
    display: block;
    margin: 0 10px;
  }

  .delete {
    color: red;
    font-weight: bold;
    font-size: 18px;
    display: inline-block;
    margin-left: 15px;
    cursor: pointer;
  }
</style>
