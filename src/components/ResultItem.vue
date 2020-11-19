<template lang="pug">
p.result
    strong &bull; {{ item.name }}
    span  {{ item.brand }}
</template>

<script>
    export default {
        props: {
            item: Object
        },
    }
</script>

<style lang="stylus">
.result
    margin 5px 0 0 0
    font-weight bold

span
    font-weight 200
</style>