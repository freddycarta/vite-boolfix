<!-- <template>
<header>
        <div>
            <input type="text" placeholder="Inserisci un titolo" v-model="query">
            <input type="button" value="Cerca" @click="fetchMovies">
        </div>
</header>
</template>

<script>
import axios from 'axios';
export default {
    data () {
        return {
            query: '',
            api_key: "e99307154c6dfb0b4750f6603256716d",
            base_url: "https://api.themoviedb.org/3"
        }
       
    },
    methods: {fetchMovies() {
            axios.get(`${this.base_url}/search/movie`, {
                params: {
                    api_key: this.api_key,
                    query: this.query
                }
            })
                .then(res => {
                console.log(res.data);
                // this.movies = res.data.results;
            });
        }

    }
}
</script>

<style lang="scss" scoped>

</style> -->