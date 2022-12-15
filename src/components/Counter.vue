<script>
import { store } from '../store'
export default {
    data() {
        return {
            store,
        }
    },
    props: {
        counter: Number,
    }
}
</script>

<template>
    <p>Trovati {{ counter }} personaggi</p>
</template>

<style lang="scss" scoped>
p {
    width: fit-content;
    margin: 20px auto;
    font-size: 1.3rem;
}
</style>