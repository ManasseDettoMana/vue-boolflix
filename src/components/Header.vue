<template>
<header>
    <div>
        <input type="text" placeholder="Cera un film o una serie TV" v-model.trim="searchField" @keyup="$emit('searching',searchField )" >
        <button class="btn btn-primary" @click="$emit('searching',searchField )">Cerca</button>
    </div>
</header>
</template>

<script>
export default {
    name: 'Header',
    data: function(){
        return{
            searchField: '',
        }
    }
}
</script>

<style lang="scss">
header{
    margin-top: 50px;
}
</style>