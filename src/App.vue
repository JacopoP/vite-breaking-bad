<script>
import axios from 'axios';
import { store } from './store'
import CardList from './components/CardList.vue'
import Filter from './components/FilterSearch.vue'
export default {
    components: {
        CardList,
        Filter,
    },
    data() {
        return {
            store,
        }
    },
    methods: {
        getFromAPI: function () {
            let myURL = store.apiURL;
            if (store.searchText != '') {
                myURL += `?status=${store.searchText}`
            }
            axios
                .get(myURL)
                .then(res => {
                    store.characterList = res.data.results;
                })
                .catch(err => {
                    console.log("Errori", err);
                });
        },
        debug: function () {
            console.log(store.searchText)
        }
    },
    mounted() {
        this.getFromAPI();
    }
}
</script>

<template>
    <h1>Rick and Morty app</h1>
    <Filter @filtertxt="getFromAPI" />
    <CardList />
</template>

<style lang="scss">
@use './style/style.scss';
</style>
