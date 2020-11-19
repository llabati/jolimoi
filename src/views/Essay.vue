<template lang="pug">
#essay
    .higher
        square-title(:title='title')
        square-img(:image='image')
    .lower
        search-bar(@new-search="getResponseFromSearch($event)")
        result-list(:answers="results")
        #more(v-if="results.length") 
            button.more-search#left(@click='goPrev') 
                strong &larr;
            span#center {{ answers.length - start }} RESULTS
            button.more-search#right(@click='goNext') 
                strong &rarr;
</template>

<script>
/* eslint-disable */
//v-if="results[i-1]" 
import SquareImg from "../components/SquareImg.vue";
import SquareTitle from "../components/SquareTitle.vue";
import SearchBar from '@/components/SearchBar.vue';
import ResultList from '@/components/ResultList.vue';
import axios from 'axios';

export default {
    data(){
        return {
            title: 'This is a page for beauty product search',
            image: '/img/beauty-products.9840c506.jpg',
            answers: [],
            results: [],
            start: 0
            //image: '../../resources/beauty-products.jpg',
            // /img/beauty-products.9840c506.jpg
        }
    },
    methods: {
        async getResponseFromSearch($event){
            await axios
                .get('https://cors-anywhere.herokuapp.com/https://skincare-api.herokuapp.com/product?q=' + $event)
                .then(res => (this.answers = res.data))
                .then(console.log('Contact'))
                .catch(error =>console.error(error))

            this.cutTheList(this.answers, this.results, 0, 'right')
            return this.results

        },
        cutTheList(origin, destination, start, direction){
            let i = start
            let j = direction === 'right' ? start + 5 : start - 5 
            this.start = j
            if (direction === 'right') {
                while (i < j && origin[i]) {
                    destination.push(origin[i])
                    i++
                }
            }
            else {
                while (i > j && origin[i]) {
                    destination.push(origin[i])
                    i--
                }
            }
            return destination
        },
        goPrev(){
            this.results = []
            this.cutTheList(this.answers, this.results, this.start)
            return this.results
        },
        goNext(){
            this.results = []
            this.cutTheList(this.answers, this.results, this.start, 'right')
            return this.results
        }
    },
    components: {
        SquareTitle,
        SquareImg,
        SearchBar,
        ResultList
    },
    mounted(){
        //this.getResponseFromSearch('laneige')
    }
}
</script>

<style lang="stylus">
$blue = #55D7FF
$red = #DB0992

.higher
    background $blue
.lower
    background $red
.more-search
    background $blue
    padding 2%
    border-radius 8%
    font-size 1em 

#more
    grid-column: 2 / 3
    grid-row: 1 / 2
    display grid
    grid-template-rows repeat(1, 1fr)
    grid-template-columns repeat(7, 1fr)
    color #FFF
    height 50%

#left {
    grid-column: 3 / 4
    grid-row: 1 / 2
    width 50%
    margin 0 auto
    }
#center {
    margin-top 5px
    grid-column: 4 / 5
    grid-row: 1 / 2
    text-align center
    margin auto 0
}
#right {
    grid-column: 5 / 6
    grid-row: 1 / 2
    width 50%
    margin 0 auto
}

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
    #more {
        grid-column: 1 / 2
        grid-row: 4 / 5

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
    #more {
        grid-column: 1 / 5
        grid-row: 4 / 5

    }
    #left {}
    #right {}

}   

</style>