<template>
	<header>
		<h1>
			<router-link to="/"> 
				<img src="../assets/3d-glasses.svg" alt="" width="80"/>
				<h3>Top Movie</h3>
			</router-link>
			
		</h1>
		
	</header> 			
</template> 

<script>

	export default {
		name: "Header",
		props: {
			title: String
		},
		data() {
			return {
				show: false
			};
		}
	}
</script>

<style scoped>
	header {
		background-color: #111;
		padding: 20px;
		color: white; 
	}
	h1 {
		margin: 0;
	}

	a {
		text-decoration: none;
	}

	h3 {
		margin: 0;
		color: #fff; 
		text-decoration:  none; 
	}

	h3 a:active {
		color: #fff;
	}

 
	h3 a:visited {
		color: #fff;
	}


</style>