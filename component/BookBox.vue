<template>
 
  

    <div v-for="book of property" :key="book.id">
        <!-- <SingleBook/> -->
        <SingleBook :book="book"/>
    </div>
     
</template>
  
  <script>
  
  import SingleBook from './SingleBook.vue'
  
   
  
  export default {
    name: 'BookBox',
    components:{
      SingleBook
    },
    props: {
        property: Array
    }

  }
  
  
  
  
  </script>
  
  
  <style>
  
  
  </style>