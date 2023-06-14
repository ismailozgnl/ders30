<template>
    <div> <SiteHeader />
        <div class="container content">
            <h1 class="title">Movies</h1>

            <input v-model="searchKeyword" type="search" placeholder="Search Movies or TV Shows">

            <div class="totalCount" id="totalCount">0 items</div>

            <div class="list" id="list"></div>
        </div>
    </div>
    <MovieCard v-for = "(movie,index) in filteredMovies"
    :key="index"
    :name="movie.Title"
    :poster="movie.Poster"
    :heighlight="searchKeyword"
    :director="movie.director"
    :year="movie.year"
    :rated="movie.rated"/>
  </template>
  
  <script>

  import { mapStores } from 'pinia';
  import { useMoviesStore } from './stores/movie';
  import SiteHeader from './components/siteHeader.vue';
  import MovieCard from './components/movieCard.vue';

  export default {
    data () {
        return {
            searchKeyword: ''
        }
    },
    
    computed : {
        ...mapStores(useMoviesStore),
        filteredMovies() {
            return this.moviesStore.movieList.filter,((item) => {
                return (new RegExp('(${this.searchKeyword})', "gi")).test(item.Title)
            })
        }
    },

    mounted () {
        this.moviesStore.getMovies()
    },

    components: {
        SiteHeader,
        MovieCard
    }
}

</script>