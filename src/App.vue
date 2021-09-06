<template>
  <div class="container">
   <Header title="Xolile Book Store"/>
   
   <AddBook @add-book="addBook"/>

   <Books @delete-book="deleteBook" :books="books"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Books from './components/Books.vue'
import AddBook from './components/AddBook.vue'

export default {
  name: 'App',
  components: {
    Header,
    Books,
    AddBook
  
  },
  data(){
    return{
      books: [],
      
    }
  },
  methods:{
    addBook(book){
      this.books = [...this.books, book]

    },
    deleteBook(id){
      if(confirm('Are you sure?')){
        this.books = this.books.filter((book) => book.id !== id)
      }    
    },
    editBook(id){
      this.Title = this.books[id].Title;
      this.editBook = id;
    }

  },

  created(){
    this.books =  [
      {
        id: 1,
        Title: 'Anna Dressed in Blood',
        Author: 'Kendare Blake',
        Genre: 'Novel, Horror fiction, Ghost story',
        Release_Date: '30 August 2011'

      },
      {
        id: 2,
        Title: 'Dracula',
        Author: 'Bram Stoker',
        Genre: 'Novel, Horror fiction',
        Release_Date: '26 May 1897'

      },
      {
        id: 3,
        Title: 'Mexican Gothic',
        Author: 'Silvia Moreno-Garcia',
        Genre: 'Horror fiction',
        Release_Date: '30 June 2020'

      },
      {
        id: 4,
        Title: 'Donners of the Dead',
        Author: 'Karina Halle',
        Genre: 'Historical Fiction',
        Release_Date: '26 February 2014'

      },
       {
        id: 5,
        Title: 'Warm Bodies',
        Author: 'Isaac Marion',
        Genre: 'Horror fiction',
        Release_Date: '10 May 2010'

      },
    ]
  }
}
</script>

<style>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
