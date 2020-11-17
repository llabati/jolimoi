<template lang="pug">
#essay
    .higher
        square-title(:title='title')
        square-img(:image='image')
    .lower
        search-bar
        result-list
     
</template>

<script>
/* eslint-disable */
import SquareImg from "../components/SquareImg.vue";
import SquareTitle from "../components/SquareTitle.vue";
import SearchBar from '@/components/SearchBar.vue';
import ResultList from '@/components/ResultList.vue';

export default {
    data(){
        return {
            title: 'This is a page for beauty product search',
            image: '/img/beauty-products.9840c506.jpg',
            //image: '../../resources/beauty-products.jpg',
            // /img/beauty-products.9840c506.jpg
        }
    },
    components: {
        SquareTitle,
        SquareImg,
        SearchBar,
        ResultList
    }
}
</script>

<style lang="stylus">
//$blue = '#55D7FF'
//$red = '#DB0992'


.lower
    background #DB0992


@media (max-width: 767px) {
    #essay {
        display grid
        grid-template-rows repeat(3, 1fr)
        grid-template-columns repeat(1, 1fr)
    }
    .higher {
        grid-column: 1 / 2
        grid-row: 1 / 3
        display grid
        grid-template-rows repeat(4, 1fr)
        grid-template-columns repeat(3, 1fr)
    }
    
    .lower {
        padding 3%
        grid-column: 1 / 2
        grid-row: 3 / 4
        display grid
        grid-template-rows repeat(4, 1fr)
        grid-template-columns repeat(1, 1fr)
    }

}
@media (min-width: 768px) {
    #essay {
        display grid
        grid-template-rows repeat(2, 1fr)
        grid-template-columns repeat(1, 1fr)
    }
    .higher {
        display grid
        grid-template-rows repeat(2, 1fr)
        grid-template-columns repeat(6, 1fr)
    }
    
    .lower {
        display grid
        grid-template-rows repeat(4, 1fr)
        grid-template-columns repeat(4, 1fr)
    }


}   

</style>