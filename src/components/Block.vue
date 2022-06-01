<template>
    <div class="block" v-if="showBlock">
        Click me
    </div>
</template>

<script>
export default {
    name: "Block",
    data() {
        return {
            showBlock: false
        }
    },
    props: ["delay"],
    mounted() {
        setTimeout(() => {
            this.showBlock = true
        }, this.delay)
        console.log("component mounted")
    },
    updated() {
        console.log("component updated")
    },
    unmounted() {
        console.log("component unmounted")
    },
}
</script>

<style scoped>
    .block {
        width: 400px;
        border-radius: 20px;
        background: #0faf87;
        color: white;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>