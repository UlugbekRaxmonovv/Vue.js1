
<template>
 <div class="app font-monospace">
<div class="content">
  <Appinfo 
  :allMovieList="moves.length"
  :favoriteMovieList="moves.filter( inx => inx.favourite).length" />
<div class="sorch-panel">
  <SorchPanel/>
  <AppFilter/>
    </div>
    <MovieList :moves="moves" 
     @onLike="onLike" />
    <MoveAddForm
     @createMovies="createMovies"
     />
  </div>
  </div>
</template>
<script>
import Appinfo from '../.././components/app-info/Appinfo.vue';
import SorchPanel from '../.././components/search-panel/SorchPanel.vue';
import AppFilter from '../.././components/app-filter/AppFiler.vue'
import MovieList from '../.././components/movie-list/MovieList.vue';
import MoveAddForm from '../../../assets/components/movie-add-form/MoveAddForm.vue'

export default {
  components: {
    Appinfo,
    SorchPanel,
   AppFilter,
    MovieList,
    MoveAddForm,
  },
     data(){
    return{
       moves:[
        {
            name:'Omar',
            viewers:811,
            like:true,
            favourite:false,
            id:1,
        },
        {
            name:'Ertigutu',
            viewers:711,
            like:false,
            favourite:true,
            id:2,
        },
        {
            name:'Sizan',
            viewers:411,
            like:true,
            favorite:false,
            id:3,
        },
        
       ],
    }
   },
   methods:{
    createMovies(etim){
     this.moves.push(etim)
    },
    onLike(id){
      const index = this.moves.map(item => {
        if(item.id == id){
          item.like = !true
        }
        return item;
      })
    }
   },
}
</script>

<style>
.app{
  height: 100vh;
  color: black;
}
.content{
  width: 1000px;
  min-height: 700px;
  background:white;
  margin: 0 auto;
  padding: 5rem 0;
}
.sorch-panel{
  margin-top:2rem;
  padding:1.5rem;
  background-color: #fcfaf5;
  border-radius:4px;
  box-shadow:15px 15px 15px rgba(0,0,0,0.15) ;
}

</style>
