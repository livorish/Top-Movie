<template>
  <ul>
  	<li v-for="movie in movies">
  		<Movie :movie="movie"/>
  	</li>
  </ul>
</template>



<script>
import Movie from './Movie.vue';
  export default {
  	name: 'MoviesList',
  	data(){
  		return{
  			movies: []
  		};
  	},
    beforeCreate() {
      console.log('beforeCreate');
    },
  	created: function(){
  		this.fetchData();
  	},
    beforeMount() {
      console.log('beforeMount');
    },
    mounted() {
      console.log('mounted');
    },
    beforeUpdate() {
      console.log('before Update');
    },
    update() {
      console.log('update');
    },
  	methods: {
    	fetchData: async function() {
      		try {
        		const res = await fetch(
  					'https://api.themoviedb.org/3/discover/movie?sort_by=popularity.desc&api_key=263bdc06ec2d5af84fb1453d61d8a359');
  				const movies = await res.json();
  				this.movies = movies.results;
  			}catch(e){
  				console.log(e);   			
  			} 
  		}
  	},

  	components: {
  		Movie
  	}

  };
</script>

<style scoped>
	ul {
		display: grid;
		list-style: none;
		padding: 1rem;
		margin: 0;
		grid-template-columns: repeat(6, 1fr);
	}

</style>
