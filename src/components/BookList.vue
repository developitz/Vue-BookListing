<template>
  <div>
    <h1>{{title}}</h1>
    <ul>
      <book-item v-for="book in books" :book="book" @deleteBook="removeBook"></book-item>
    </ul>
    <hr>
    <book-form @addBook="appendBook"></book-form>
  </div>
</template>

<script>
  import BookItem from './BookItem';
  import BookForm from './BookForm';

  export default {
    name: 'BookList',
    components: {
      BookItem,
      BookForm,
    },
    data() {
      return {
        title: 'All Books',
        books: [
          {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
          {title: 'American Gods', author: 'Neil Gaiman'},
          {title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
        ],
      };
    },
    methods: {
      appendBook(bookTitle, bookAuthor) {
        this.books.push({
          title: bookTitle,
          author: bookAuthor,
        });
      },
      removeBook(book) {
        const position = this.books.indexOf(book);

        if (position > -1) {
          this.books.splice(position, 1);
        }
      },
    },
  };
</script>

<style>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }
</style>
