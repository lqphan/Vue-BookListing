<template>
    <div>
            <h1>{{title}}</h1>
     <ul>
                 <book-item v-for="book in books" :book='book'></book-item>
                
    </ul>
    <hr>
    <book-form @addBook='appendBook'></book-form>
 </div>   
</template>


<script>
import BookForm from './BookForm';
import BookItem from './BookItem'; 
export default {
    name: 'BookList',
    components: {
        BookItem,
        BookForm
    },
    data() {
        return {title: 'All Books', 
        books:[
        {title: 'Self-Reliance', author: 'Ralph Walk Emerson'},
        {title: 'American Gods', author: 'Neil Gaiman'},
        {title: 'Amusing Ourselves to Death', author: 'Neil Postman'}
        ]
        }
    },
    methods: {
        appendBook(bookTitle, bookAuthor){
            this.books.push({title: bookTitle, author: bookAuthor})
        }
    }
}
</script>

<style>
h1,
h2 {
  font-weight: 400;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>
