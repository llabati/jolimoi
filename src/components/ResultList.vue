<template lang="pug">

ul#list
    li
        result-item &bull; Labati Pascal
    li
        result-item &bull; Ruby Eloi
    li
        result-item &bull; Viguier Nastya
        
</template>

<script>
    import ResultItem from './ResultItem';
    export default {
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
    font-size 1.8em
    color #FFF

@media (max-width: 767px) {
    #list {
        grid-column: 1 / 2
        grid-row: 2 / 5
    }
    
}
@media (min-width: 768px) {
    #list {
        grid-column: 2 / 4
        grid-row: 2 / 5
    }
    
}  

</style>