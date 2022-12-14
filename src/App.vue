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
    },
    methods: {
        getFromAPI: function () {
            axios
                .get(store.apiURL)
                .then(res => {
                    store.characterList = res.data.results;
                })
                .catch(err => {
                    console.log("Errori", err);
                });
        }
    },
    mounted() {
        this.getFromAPI();
    }
}
</script>

<template>
    <h1>Rick and Morty app</h1>
    <CardList />
</template>

<style lang="scss">
@use './style/style.scss';
</style>
