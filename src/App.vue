<script>
import axios from 'axios';
import { store } from './store'
import CardList from './components/CardList.vue'
import Filter from './components/FilterSearch.vue'
import Counter from './components/Counter.vue'
export default {
    components: {
        CardList,
        Filter,
        Counter,
    },
    data() {
        return {
            store,
            x: 0,
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
        changeNumber: function () {
            return this.store.characterList.length;
        }
    },
    mounted() {
        this.getFromAPI();
    }
}
</script>

<template>
    <h1>Rick and Morty app</h1>
    <Filter @filtertxt="getFromAPI(); changeNumber();" />
    <CardList />
    <Counter :counter="changeNumber()" />
</template>

<style lang="scss">
@use './style/style.scss';
</style>
