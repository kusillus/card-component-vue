<template>
	<div :style="background_style"
		class="card_container"
		@click="onClick(id)">
		<div class="card_content">
			<div class="text_top">
				{{title | limit(25)}}
			</div>
			<div class="text_bottom">
				{{content | limit(80)}}
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		props: ['title', 'content', 'img', 'id'],
	  	data () {
	    	return {
	      	background_style: {
	      		background: 'linear-gradient(rgba(9, 0, 21, 0.7) 10%, rgba(0, 0, 0, 0) 20%, rgba(0, 0, 0, 0) 50%, rgba(18, 3, 39, 0.8) 80%), url("'+  require('../assets/'+ this.img) +'")',
	      		backgroundSize: 'cover',
				backgroundPosition: 'center'
	      		}
	    	}
	  	},
	  	methods: {
	  		onClick: function (id) {
	  			console.log('Pokemon id: ' + id)
	  		}
	  	},
	  	filters: {
	  		limit: function (text, length) {
	  			console.log('filter')
	  			let limitCount = parseInt(length, 10)
	  			if(limitCount <= 0) {
	  				return text
	  			}
	  			if(text.length > length) {
	  				return text.slice(0, limitCount) + '...'	
	  			} else {
	  				return text	
  				}
  			}
	  	}
	}
</script>
<style lang="scss">
 @import url('https://fonts.googleapis.com/css?family=Gugi');
 @import url('https://fonts.googleapis.com/css?family=Exo+2');
	.card_container{
		width: 17rem;
		height: 25rem;
		margin: 0 .5rem 1rem 0;
		background-size: cover;
		background-position: center;
		color: white;
		border-radius: .8rem;
		box-shadow: 0px 0px 15px 1px #0000004d;
		cursor: pointer;
		transition: all .3s ease;
	}
	.card_content{
		text-align: left;
		padding: 1rem;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		box-sizing: border-box;
	}
	.text_top{
		font-weight: bold;
		font-family: 'Gugi', cursive;
	}
	.text_bottom{
		font-weight: 300;
    	font-family: 'Exo 2', sans-serif;
    	text-align: center;
	}
	.card_container:hover{
		filter: brightness(140%);
		// animation-name: changeLight;
  //   	animation-duration: 1s;
  //   	animation-iteration-count: infinite;
	}
	// Puedes habilitar el efecto descomentando las lienas anteriores
	@keyframes changeLight {
	    0% {filter: brightness(140%);}
	    // 10% {filter: brightness(120%);}
	    // 12% {filter: brightness(140%);}
	    // 40% {filter: brightness(130%);}
	    // 42% {filter: brightness(110%);}
	    50% {filter: brightness(120%);}
	    // 52% {filter: brightness(110%);}
	    // 60% {filter: brightness(140%);}
	    // 72% {filter: brightness(110%);}
	    100% {filter: brightness(140%);}
	}
</style>