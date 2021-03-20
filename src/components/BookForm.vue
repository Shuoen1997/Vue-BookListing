<template>
  <form @submit.prevent="bookSubmit(bookTitle, bookAuthor)" class="" action="#" method="post">
    <input v-model="bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <button type="submit" name="button">Add Book</button>
  </form>
</template>
<script>
export default {
  name: 'BookForm',
  methods: {
    bookSubmit(bookTitle, bookAuthor) {
      this.$emit('addBook', bookTitle, bookAuthor);
    }
  },
  data: function () {
    return {bookTitle: '', bookAuthor: ''}
  },
  props: ['books']
}
</script>
<style></style>
