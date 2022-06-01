<template>
    <p>Reaction time score: {{ score }}</p>
    <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    name: "Result",
    props: ["score"],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
        if(this.score < 250) {
            this.rank = "Ninja Fingers"
        } else if (this.score < 400) {
            this.rank = "Rapid Reflexses"
        } else {
        this.rank = "Snail pace"
        }
    }
}
</script>

<style scoped>
    .rank {
        font-size: 1.4em;
        color: #0faf87;
        text-align: center;
        font-weight: 700;
    }
</style>