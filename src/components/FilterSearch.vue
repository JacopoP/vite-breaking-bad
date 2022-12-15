<script>
import { store } from '../store'
export default {
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <select @change="$emit('filtertxt')" v-model="this.store.searchText">
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