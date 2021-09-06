<template>
 <div @dblclick="$emit('toggle-reminder', book.id)" class="book">
        <h3>{{ book.Title }}
        <i @click="$emit('delete-book', book.id)"  class="fas fa-times"></i>

        
    </h3>
    <p>{{ book.Author }}</p>
    <p>{{ book.Genre }}</p>
    <p>{{ book.Release_Date }}</p>
</div>   
</template>

<script>
export default {
    name: 'Book',
    props: {
        book: Object
    },

}
</script>

<style scope>
.fas{
    color: blue;
}

.book{
    background: whitesmoke;
    margin: 7px;
    padding: 12px 22px;
    cursor: pointer;
}

.book .reminder{
    border-left: 6px solid green;
}

.book h3{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>