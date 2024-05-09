<template lang="">
    <ul  v-bind:movie="movie" class="move-list list-group">
        <MoveListEtim v-for="movie in moves" v-bind:movie="movie"/>
    </ul>
</template>

<script>
import MoveListEtim from '../../components/move-list-etim/MoveListEtim.vue'
export default {
    components: {
        MoveListEtim
    },
    props: {
       moves:{
        type: Array,
        required:true,
       },
    },

}
</script>
<style scoped>

  .move-list{
    margin-top:2rem;
       padding:1.5rem;
       background-color: #fcfaf5;
       border-radius:4px;
       box-shadow:15px 15px 15px rgba(0,0,0,0.15) ;
  }  
</style>