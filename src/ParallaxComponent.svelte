<script>
	//https://github.com/wagerfield/parallax#11-installation
	import Parallax from 'parallax-js'; 

	import {slide} from 'svelte/transition'

	let images = 
	[
	
	
		'images/RING-hero.svg',
		'images/radial-inner-ring.svg',
		'images/dotted-ring.svg',
		' images/radial-circle.svg',
		' images/Frame.svg',
		' images/Reticle.svg',
	]

	let size = '50vw';

	let scene, parallaxInstance

	const ready = node => {
		console.log(node)
		parallaxInstance = new Parallax(node)
		parallaxInstance.scalar(5.0)
		parallaxInstance.invert(false, false);
	}

	let showHappening = false
</script>

<main class="parallax-container">
	<section class="parallax"  style="--ring-size:{size}" >	
		<div use:ready class='container '>
			 
			<!-- While all other options and parameters are optional, with sane defaults, and can be set programatically, each layer needs a data-depth attribute. The movement applied to each layer will be multiplied by its depth attribute. -->
			{#each images as image, index}
			<div data-depth='{index + .6}' >
				<img src='{image}' alt='' class='rotating-ring{index}' > 
			 
			</div>
			{/each}
	<!-- <div class="hero-image"></div> -->
		</div>
	</section>
 
 
</main>
<style>
	:root {
  --ring-size:50vw;
}

	img{
		width:var(--ring-size);
	} 
	
.hero-image {
	border-radius: 50%;
	background: white;
	position: absolute;
	right:0px;
	left:0px;
	top:0px;
	bottom: 0px;
	width:250px;
	height:250px;
	margin:auto;
	z-index: 11;
	overflow: hidden;
	opacity: .1;
}
	.parallax{
		width:100%;
		height:100%;
 		opacity: 0.2;
		display:grid;
		place-items:center;
		transition: all 1s;
		margin-top:  100px;
		color:white;
	} 

	.parallax .container {
		margin-bottom: 140px;;
	}
	.parllax:hover{
		opacity: .6;
	} 
	main img{

		max-width:var(--ring-size);	
		animation:ring-appear 30s linear infinite;
		-webkit-animation: hero-ring-appear 30s linear infinite;
		-moz-animation: hero-ring-appear   30s linear infinite;
		animation-delay: 5s;
 		 animation-direction: reverse;
	} 
	.rotating-ring0{
		max-width:var(--ring-size);
		padding:  0px;
		animation:ring-appear 20s linear infinite;
		-webkit-animation: hero-ring-appear 20s linear infinite;
		-moz-animation: hero-ring-appear   20s linear infinite;
		animation-delay: 5s;
		transform: scale(0.75);
	} 
	.rotating-ring1{
		max-width:var(--ring-size);
		padding:  50px;
		animation:ring-appear 20s linear infinite;
		-webkit-animation: hero-ring-appear 20s linear infinite;
		-moz-animation: hero-ring-appear   20s linear infinite;
		animation-delay:  5s;
		transform: scale(0.75);
	} 
	.rotating-ring2{
		padding:10px;
		animation:ring-appear 20s linear infinite;
		-webkit-animation:ring-appear 20s linear infinite;
		-moz-animation: ring-appear   20s linear infinite;
 		 animation-direction: reverse;
		  max-width:var(--ring-size);  
		
 
		 
		
	} 
	.rotating-ring3{
		max-width:var(--ring-size);
		padding:170px;
		animation : hero-ring-appear  15s linear infinite;
		-webkit-animation: hero-ring-appear  15s linear infinite;
  -moz-animation: hero-ring-appear   15s linear infinite;
   
	 
	
	}
	.rotating-ring4 {
		max-width:var(--ring-size);
		padding:350px;
		animation : hero-ring-appear  15s linear infinite;
		-webkit-animation: hero-ring-appear  15s linear infinite;
  -moz-animation: hero-ring-appear   15s linear infinite;
  animation-direction: reverse;
  
   
	}
	.rotating-ring5 {
		width:var(--ring-size);
	 
		animation : hero-ring-appear  25s linear infinite;
		-webkit-animation: hero-ring-appear  25s linear infinite;
  -moz-animation: hero-ring-appear   25s linear infinite;
  animation-direction: reverse;
  
   
	}

  .ring-appear{
	animation :  ring-appear  1s linear infinite;
	-webkit-animation: ring-appear 1s linear forwards;
 	-moz-animation: ring-appear  1s linear forwards;
	
  }
  @media screen and (max-width: 800px) {
    :root {
		--ring-size:100vh;
    }

	.parallax{
		animation: fadeinout 2s;
		margin-top:  50%;
		color:white;
		transform:scale(2);
	} 
	main.parallax-container {
  height: 100vh;
  position: absolute;
  width: 100%;
  top: 0px;
  margin-top: -50%;
}
.hero-interactive 
{
	margin-top: 100%;;
}
	
}
 
@media screen and (min-width: 1600px) {
    :root {
		--ring-size:100vh;
    }

	.parallax{
		animation: fadeinout 2s;
		margin-top:-10vw;
		color:white;
		opacity:.3;
		transform:scale(0.6);
	} 
	
}


  
@keyframes hero-ring-appear {
  from {
 
	-webkit-transform: rotate(0deg) scale(.75);
	  -o-transform: rotate(0deg) scale(.75);
	  transform: rotate(0deg) scale(.75);
	  opacity:.5;
  } 
  20% {
    transform: rotate( -160deg)  scale(.55);
  
  }  30% {
    transform: rotate( 260deg) scale(.4);
  
  }
  70% {
    transform: rotate( 60deg) scale( .6);
  
  }
 75% {
    transform: rotate( 160deg) scale( .45);
    opacity:1;
  }
 95% {
    transform: rotate( -160deg) scale( .85);
  opacity:0.6;
  }
 to {
 
	-webkit-transform: rotate(360deg) scale(.75);
	  -o-transform: rotate(360deg) scale(.75);
	  transform: rotate(360deg) scale(.75);
	  opacity:.5;
  } 
}
@keyframes ring-appear {
  from {
 
	-webkit-transform: rotate(0deg) scale(0.5);
	  -o-transform: rotate(0deg) scale(0.5);
	  transform: rotate(0deg) scale(0.5);
	  opacity:.3;
  } 
  20% {
    transform: rotate( -160deg)  scale(.55);
	opacity: .3;
  
  }  30% {
    transform: rotate( -260deg) scale(.2);
  
  }
  70% {
    transform: rotate( 60deg) scale( .1);
	opacity:1;
  }
  70% {
    transform: rotate( 160deg) scale( .45);
  
  }
 to {
 
	-webkit-transform: rotate(360deg) scale(0.5);
	  -o-transform: rotate(360deg) scale(0.5);
	  transform: rotate(360deg) scale(0.5);
	  opacity: .3;
  } 
}
</style>