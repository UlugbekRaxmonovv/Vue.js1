<template>
    <li class="list-group-etim d-flex justify-content-between" 
    :class="[{like: movie.like}],{favourite: movie.favourite}">
        <span v-on:click='onLike' class="list-group-etim-label"> {{ movie.name }}</span>
        <input type="number"   class="list-group-etim-input" v-bind:value="movie.viewers"/>
        <div class="d-flex justify-content-center align-items-center"> 

            <button type="button" class="btn-cookie btn-sm">
                <i class="fas fa-cookie"></i>
            </button>

            <button type="button" class="btn-trash btn-sm">
                <i class="fas fa-trash"></i>
            </button>
            <i class="fas fa-star"></i>
        </div>
    </li>

</template>
<script>
export default {
    props:{
        movie:{
            type:Object,
            required:true,
        },
    },
    methods:{
        onLike(){
        this.$emit('onLike', this.movie.id);
        }
}
}
</script>
<style scoped>
    .list-group-etim{
        padding: 15px 20px;
        border-bottom: 1px solid #3d5a80;
        border:none;
    }
    .list-group-etim:last-child{
   border-bottom:none;
    }
    .list-group-etim span{
        line-height:35px;
font-size:20px;
cursor:pointer;
width:550px;
    }
.list-group-etim input{
    line-height:35px;
font-size:20px;
text-align:center;
border:0;
outline:none;
background-color: #fcfaf5;

}
.list-group-etim button{
    width:35px;
    height:35px;
    margin:3px;
    font-size:17px;
    border:none;
    cursor:pointer;

}
.list-group-etim  .btn-cookie{
    color:#e09f3e;
}
.list-group-etim  .btn-trash{
    color:#e5383b;
}
.list-group-etim  .fa-star{
    color:#ffd700;
    width:35px;
    height:35px;
    text-align:center;
    line-height:35px;
    font-size:16px;
    transition: .3s all;
    transform: translate(30px);
    opacity: 0;
}
.list-group-etim.like  .fa-star{
    opacity:1;
    transform: translateX(0);
}
.list-group-etim.favourite .list-group-etim-label,
.list-group-etim.favourite .list-group-etim-input{
     color:#e09f3e;
}
    
</style>