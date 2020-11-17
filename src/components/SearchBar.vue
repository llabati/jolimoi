<template lang="pug">
form(action="" method="method")
    input.search(placeholder="Type your search here")
    button.btn-search(type='submit') Search
</template>

<script>
    export default {
        
    }
</script>

<style lang="stylus">
form
    //width 50%
    //height 100px
    margin 0
    padding 0
    display grid
    grid-template-columns repeat(20, 1fr)
    grid-template-rows repeat(2, 50%)

    .search
        grid-column 1 / 16
        grid-row 2 / 3
        padding 2%
        border-radius 8%
        font-size 1.4em 

    .btn-search
        grid-column 17 / 21
        grid-row 2 / 3
        background #55D7FF
        padding 2%
        border-radius 8%
        font-size 1.4em 

@media (max-width: 767px) {
    form {
        grid-column: 1 / 2
        grid-row: 1 / 2
    }
    
}
@media (min-width: 768px) {
    form {
        grid-column: 2 / 4
        grid-row: 1 / 2
    }
    
}  
</style>