<template lang="pug">
.square
    .title
        h1 {{ title }}
</template>

<script>
    export default {
        props: {
            title: String
        } 
    }
</script>

<style lang="stylus">
.square
    display flex
    width: 100%
    flex-direction column
    justify-content center
    align-items center
    background-color #55D7FF

.title
    text-align center
    width 50%

h1
    font 1.4em 
    font-weight bold

@media (max-width: 767px) {
    .square {
        grid-column: 1 / 4
        grid-row: 1 / 3
    }
    
}
@media (min-width: 768px) {
    .square {
        grid-column: 1 / 4
        grid-row: 1 / 3
    }
    
}   


</style>