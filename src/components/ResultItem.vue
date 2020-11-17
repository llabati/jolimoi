<template lang="pug">
p.result
    slot 
        strong
        span
</template>

<script>
    export default {
        
    }
</script>

<style lang="stylus">
.result
    margin 5px 0 0 0
    font-weight bold
</style>