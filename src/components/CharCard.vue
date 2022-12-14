<script>
export default {
    props: {
        char: Object,
    }
}
</script>

<template>
    <div class="card">
        <img :src="char.image" :alt="char.name">
        <h3>{{ char.name }}</h3>
        <div id="status">{{ char.status }}</div>
        <div>{{ char.species }}</div>
    </div>
</template>

<style lang="scss" scoped>
.card {
    text-align: center;

    img {
        border-radius: 50%;
    }

    h3 {
        font-size: 1.3rem;
        margin: 15px 0;
    }

    div {
        font-size: 1.1rem;

        &#status {
            margin-bottom: 5px;
        }
    }
}
</style>