<script>
import { store } from '../store'
export default {
    data() {
        return {
            aux: '',
        }
    },
    methods: {
        getFilterText: function () {
            store.searchText = this.aux;
        }
    }
}
</script>

<template>
    <select @change="getFilterText(); $emit('filtertxt');" id="ciao" v-model="this.aux">
        <option value="">All</option>
        <option value="alive">Alive</option>
        <option value="dead">Dead</option>
        <option value="unk">Unknown</option>
    </select>
</template>

<style lang="scss" scoped>
select {
    display: block;
    margin: 40px auto;
    font-size: 1.5rem;
    padding: 5px 20px 5px 3px;
}
</style>