<template>
    <div class="movie-add-form">
        <h3>Yangi kino qoshish </h3>
        <form class="add-form d-flex" v-on:submit.prevent>
            <input type="text" 
            placeholder="Qanay kino?" class="form-control new-movie-label" 
             v-bind:value="name"   
             @input= "name = $event.target.value" />

              <!-- inputan qiymat olish -->
            <input type="number" 
            placeholder="Nechi marotaba ko'rilgan?"
             class="form-control new-movie-label"
              v-bind:value="viewers"
              @input= "viewers = $event.target.value" />
              
              <button class="btn btn-outline-dark" type="submit"  v-on:click="AddMove" >Qo'shish</button>
        </form>
    </div>
</template>
<script>
export default {
    data(){
        return {
            name: '',
            viewers: '',
        }
    },
    methods: {
    AddMove(e){
        const newData={
               name:this.name,
            viewers:this.viewers,
            like:false,
            favourite:false,
        }
        this.$emit('createMovies', newData)
             this.name =""
             this.viewers =""
       
},
}
}
</script>
<style scoped>
   .movie-add-form{
       margin-top:2rem;
       margin-bottom:1rem;
       padding:1.5rem;
       background-color: #fcfaf5;
       border-radius:4px;
       box-shadow:15px 15px 15px rgba(0,0,0,0.15) ;
   } 
</style>