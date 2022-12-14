<script>
import axios from 'axios';
import { store } from './store'
import CardList from './components/CardList.vue'
export default {
    components: {
        CardList,
    },
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <h1>Rick and Morty app</h1>
    <p v-for="a in store.characterList">Ciao</p>
</template>

<style lang="scss">
@use './style/style.scss';
</style>
