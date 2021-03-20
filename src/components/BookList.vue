<template>
  <div>
    <h1>
      {{ title }}
    </h1>
    <ul>
      <book-item :book="book" v-for="book in books" >
      </book-item>
<!--      <li>-->
<!--        Book 1-->
<!--      </li>-->
<!--      <li>-->
<!--        Book 2-->
<!--      </li>-->
<!--      <li>Book 3</li>-->
    </ul>
  <book-form @addBook="appendBook"></book-form>
  </div>
</template>
<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm";
export default {
  name: 'BookList',
  components: {BookForm, BookItem},
  methods: {
    appendBook(bookTitle, bookAuthor){
      this.books.push({ title: bookTitle, author: bookAuthor })
    }
  },
  data: function () {
    return {
      title: 'All Books', books: [
        {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
        {title: 'American Gods', author: 'Neil Gaiman'},
        {title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
      ]
    }
  }
}
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
