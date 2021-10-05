<template>
    <div class="col-3 col-xs-12 carta">
        <h1>{{movie.title}}</h1>
        <h2><small>{{movie.original_title}}</small></h2>
        <img v-if="movie.original_language == 'it'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/800px-Flag_of_Italy.svg.png" alt="">
        <img v-else-if="movie.original_language == 'en'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Flag_of_the_United_Kingdom_%283-5%29.svg/800px-Flag_of_the_United_Kingdom_%283-5%29.svg.png" alt="">
        <h3>{{movie.vote_average}}</h3>
        <i v-if="isActive" class="far fa-star" @click="starClick"></i>
        <i v-else class="fas fa-star active" @click="starClick"></i>
        
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: ['movie'],
    data: function(){
        return{ 
            isActive: true,

        }
    },
    methods: {
        starClick: function(){
            this.isActive=!this.isActive;
        }
    }
}
</script>

<style scoped lang="scss">
@import "~@fortawesome/fontawesome-free/css/all.css";
.carta{
    background-color: rgb(65, 65, 65);
    color: white;
    i{
        transform: scale(1.5)    
    }
    img{
        height: 50px;
        width: 50px;
    }
    .active{
        color: goldenrod;
    }

}

</style>