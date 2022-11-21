<template>
    <li>
        <h3>{{movie.title}}</h3>
        <p>{{movie.original_title}}</p>
        <p>{{movie.original_language}}</p>
        <p>{{movie.vote_average}}</p>
    </li>
   
</template>

<script>
export default {
    props: {
        movie: {
            type: Object,
        }
        
    }
}
</script>

<style lang="scss">


// img {
//     border-radius: 50%;
//     box-shadow: 0 0 6px 3px rgba(#000, 0.15);
// }
</style>