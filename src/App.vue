<template>
    <h1>Boolfix</h1>
    <div id="app">
        <ul>
            <li v-for="movie in movies" :key="movie.id">
                {{ movie.original_title }}
            
            </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios';

// import { store } from './store';

export default {
    name: 'app',
    data() {
        return {
            movies: [],
            api_key: 'e99307154c6dfb0b4750f6603256716d',
            query: 'return',
            base_url:'https://api.themoviedb.org/3'
        }
    },

    methods: {
        fetchMovies () {
            axios.get(`${this.base_url}/search/movie?api_key=${this.api_key}&query=${this.query}`)
            .then ((res) => {
                console.log(res)
                this.movies = res.data.results
            })
        }
    },
    created () {
        this.fetchMovies()

    },
};
</script>

<style lang="scss">

</style>

