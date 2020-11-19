<template lang="pug">

ul#list
    li(v-for="item in answers")
        result-item(:item="item") 
    
        
</template>

<script>
    import ResultItem from './ResultItem';
    export default {
        props: {
            answers: Array
        },
        components: {
        ResultItem
    }
    }
</script>

<style lang="stylus">
#list
    list-style-type none
    margin 15px 0 0 0
    padding 0
    text-align left
    font-size 1.4em
    color #FFF

@media (max-width: 767px) {
    #list {
        grid-column: 1 / 2
        grid-row: 2 / 4
    }
    
}
@media (min-width: 768px) {
    #list {
        grid-column: 2 / 4
        grid-row: 2 / 4
    }
    
}  

</style>