<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <Pokemon />
    </div>
</template>

<script>
import Pokemon from './components/Pokemon.vue'

export default {
    name: 'App',
    components: {
        Pokemon,
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

tr td {
    padding: 5px;
    border: 1px solid gray;
}

tr th {
    padding: 5px;
    border: 1px solid gray;
}

tr th.head {
    background-color: black;
    color: white;
}

</style>
