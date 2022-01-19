<script>
	export let sideCardText;
	export let backCardText;
	export let src;

	let flipped = true
	
	function flip(node, {
		delay = 0,
		duration = 650
	}) {
		return {
			delay,
			duration,
			css: (t, u) => `
				transform: rotateY(${1 - (u * 180)}deg);
				opacity: ${1 - u};
			`
		};
	}

</script>


<style>
	
	* {

		text-align: center;

		}


	.card-container {
		position: relative;
		height: 300px;
		width: 300px;
		display: inline-block;

	}
	
	.card {
		width: 100%;
		height: 100%;
		position: absolute;
		perspective: 600;
		border:none;
	}
	
	.side {
		position: absolute;
		height: 100%;
		width: 100%;
		background-color: rgb(255, 0, 0);
		overflow: hidden;
		color: #fff;
		justify-content: center;
		align-items: center;
		text-align: center;
		font-size: large;
  		font-weight: bold;
		  
		  
  		
	}

	.side-text {
		margin-left: 70px;
		margin-right: 70px;
		margin-top: 0px;
		width: 150px;
		
	}
	
	.back {
		display: flex;
		position: absolute;
		height: 100%;
		width: 100%;
		background-color: rgb(255, 0, 0);
		overflow: hidden;
		color: #fff;
		justify-content: center;
		align-items: center;
		text-align: center;
		font-size: large;
  		font-weight: bold;
		background-image: url('https://xtratheme.com/elementor/interior/wp-content/uploads/sites/3/2017/08/img5-1.jpg');
		background-position: center center;
  		background-size: contain;
		
  		
	}

	.back p {
  		color: rgb(255, 255, 255) !important;
  		font-weight: bold;
 		opacity: 1 !important;
		
	}
	.logo {
		width: 10%;
		margin-top: 85px;
		
		
	}
</style>

<div class="card-container" on:mouseenter={() => flipped = !flipped} on:mouseleave={() => flipped = !flipped}>
	<div class="card">
		{#if flipped}
		<div class="side" transition:flip>
			<img class="logo" {src} alt="Logo">

				<p class="side-text">{sideCardText}</p>
		</div>
		{:else}
		<div class="back" transition:flip>
			<p>{backCardText} </p>
		</div>
		{/if}
	</div>
</div>
