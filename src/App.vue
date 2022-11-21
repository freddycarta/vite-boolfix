<template>
    <h1>Boolfix</h1>
    <div id="app">
        <div>
            <input type="text" placeholder="Inserisci un titolo" v-model="query">
            <input type="button" value="Cerca" @click="fetchMovies">
        </div>
    
        <ul>
            <CardComponent v-for="movie in movies" :key="movie.id" :movie="movie"></CardComponent>
        </ul>
    </div>
</template>

<script>
import axios from 'axios';
import CardComponent from './components/CardComponent.vue';


export default {
    name: "app",
    data() {
        return {
            movies: [],
            api_key: "e99307154c6dfb0b4750f6603256716d",
            query: "Cerca",
            base_url: "https://api.themoviedb.org/3"
        };
    },
    methods: {
        fetchMovies() {
            axios.get(`${this.base_url}/search/movie`, {
                params: {
                    api_key: this.api_key,
                    query: this.query
                }
            })
                .then(res => {
                console.log(res.data);
                this.movies = res.data.results;
            });
        }
    },
    components: { CardComponent }
}
</script>

<style lang="scss">
#app {
    margin-top: 30px;
}

</style>

