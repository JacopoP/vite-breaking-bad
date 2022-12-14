<script>
import { store } from '../store.js'
import Card from './CharCard.vue';
export default {
    components: {
        Card,
    },
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div id="container">
        <Card v-for="character in store.characterList" :char="character" :key="character.name" />
    </div>
</template>

<style lang="scss" scoped>
#container {
    display: flex;
    gap: 50px;
    max-width: 1400px;
    margin: 0 auto;
    justify-content: space-around;
    flex-wrap: wrap;
}
</style>