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
    width: 100%
    display grid
    grid-template-columns repeat(4, 1fr)
    grid-template-rows repeat(3, 1fr)

.title
    grid-column 2 / 4
    grid-row 2 / 3
    padding-top 7%

h1
    text-align center
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