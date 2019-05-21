<template>
  <form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)" class="" action="#" method="post">
    <input v-model="bookTitle" type="text" name="title" value="" placeholder="Titel">
    <input v-model="bookAuthor" type="text" name="author" value="" placeholder="Autor">
    <button type="submit" name="button">Buch hinzufügen</button>
  </form>
</template>

<script>
  export default {
    name: "BookForm",
    props: ["books"],
    data() {
      return {
        bookTitle: '',
        bookAuthor: '',
      };
    },
    methods: {
      bookSubmit(bookTitle, bookAuthor) {
        this.$emit('addBook', bookTitle, bookAuthor);
      },
    },
  };
</script>

<style scoped>

</style>
