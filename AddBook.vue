<template>

  <form @submit="onSubmit"  class="add-form">
      <div class="form-control">
          <label>Book</label>
          <input type="text" v-model="Title"  name="Title" placeholder="add_title" />
      </div>

       <div class="form-control">
          <label>Author</label>
          <input type="text"  v-model="Author" name="Author" placeholder="add_author" />
      </div>

      <div class="form-control">
          <label>Genre</label>
          <input type="text"  v-model="Genre" name="Genre" placeholder="add_genre" />
      </div>

       <div class="form-control">
          <label>Release_Date</label>
          <input type="text" v-model="Release_Date" name="Release_Date" placeholder="add_release_date" />
      </div>  
      
      <input type="submit" value="save book" class="btn btn-block" />

  </form>

</template>

<script>
export default {
    name: 'AddBook',
    data(){
        return{
            Title: '',
            Author: '',
            Genre: '',
            Release_Date: ''
        }
    },
    methods:{
        onSubmit(e){
            e.preventDefault();
            
            if(!this.Title){
                arlet('Please add a Book')
            }
            const newBook = {
                id: Math.floor(Math.random() * 1000),
                Title: this.Title,
                Author: this.Author,
                Genre: this.Genre,
                Release_Date: this.Release_date

            }

            this.$emit('add-book', newBook)

            this.Title = ''
            this.Author = ''
            this.Genre = ''
            this.Release_Date = ''
        }
    }
}
</script>

<style>

.add-form{
    margin-bottom: 20px;    
}

.form-control{
    margin: 20px 0;
}

.form-control label{
    display: block;
}

.form-control input{
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}
.form-control-check{
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
}

.form-control-check label{
    flex: 1;
}

.form-control-check input{
    flex: 2;
    height: 20px;
}
</style>