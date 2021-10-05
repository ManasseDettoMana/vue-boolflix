<template>
<header>
    <div>
        <input type="text" placeholder="Cera un film o una serie TV" v-model="searchField" @keyup.enter="searchMovie(searchField)">
        <button class="" @click="searchMovie(searchField)">Cerca</button>
    </div>
</header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style>

</style>