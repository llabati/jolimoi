<template lang="pug">
#form
    input.search(type='text' name='name' placeholder="Brand, product, ingredient: type your search here" v-focus v-model="query")
    button.btn-search(type='submit' @click='send') Search
</template>

<script> 
    export default {
        data(){
            return {
                query: ''
            }
        },
        methods: {
            send(){
                
                console.log(this.query)
                this.$emit('new-search', this.query)
            }
        },
        directives: {
            focus(el){
                el.focus()
            }
    }
    
    } 
</script>

<style lang="stylus">
#form
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
    #form {
        grid-column: 1 / 2
        grid-row: 1 / 2
    }
    
}
@media (min-width: 768px) {
    #form {
        grid-column: 2 / 4
        grid-row: 1 / 2
    }
    
}  
</style>