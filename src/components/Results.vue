<template>
    <p>Reaction time score: {{ score }}</p>
</template>

<script>
export default {
    name: "Result",
    props: ["score"],
}
</script>