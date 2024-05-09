<template>
<div class="app-info ">
    <p class="fs-3 text-uppercase">Barcha kinolar soni:  {{allMovieList}}</p>
    <p  class="fs-4 text-uppercase"> Kurilgan kinolar soni: {{favoriteMovieList}}</p>
    </div>
</template>

<script>
export default{
  props: {
    allMovieList:{
      type: Number,
      required:true,
    },
    favoriteMovieList:{
      type: Number,
      required:true,
    },
  },
}

</script>

<style scoped>
.app-info{    
    padding:1.5rem;
  background-color: #fcfaf5;
  border-radius:4px;
  box-shadow:15px 15px 15px rgba(0,0,0,0.15) ;
}
</style>