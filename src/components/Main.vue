<template>
    <main>
        <h2>Risultato della ricerca</h2>
        <div class="container">
            <div class="row">
                <Card v-for="movie in movies" :key="movie.id" :movie="movie"/>
            </div>
        </div>
    </main>
</template>

<script>
import Card from './Card.vue'
export default {
    name: 'Main',
    props: {
        "movies": Array,
    },
    data: function(){
        return{
        }
    },
    components: {
        Card,
    }
    
}
</script>

<style lang="scss" scoped>
@import '~bootstrap/scss/bootstrap.scss'
</style>