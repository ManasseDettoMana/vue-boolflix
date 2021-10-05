<template>
    <div class="col-3">
        <h1>{{movie.title}}</h1>
        <h2>{{movie.original_title}}</h2>
        <h2>{{movie.original_language}}</h2>
        <h3>{{movie.vote_average}}</h3>
        
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: ['movie']
}
</script>

<style>

</style>