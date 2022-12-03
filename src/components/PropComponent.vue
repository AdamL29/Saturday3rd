<template>
    <div>
        {{counter}}
        <h1>{{customString}}</h1>
    </div>
</template>

<script>
    export default {
        name : "PropComponent",
        props: {
            counter: Number,
            customString: String,
        },
    }
</script>

<style scoped>

</style>