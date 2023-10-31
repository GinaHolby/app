<script>
  export let data;



</script>

<svelte:head> <title> Oppskrifter </title></svelte:head>
  


<div class="homepage">

	<section class="hero">

		<a class="title" >
			<h1 class="herotext">Gina Holby</h1>
			<h3 class="subherotext">UX-designer og frontend-utvikler</h3>
		</a>

		<div class="skoleoppgaver">
			{#each data.projects as project}

				<a class="" href="/project/{project.slug.current}">
					<img class="{project.bublePlacement ?? "hide"} circle" src="{project.bilde}" alt="">
				</a>

			{/each}
		</div>

	</section>


</div>


<style>
	.homepage{
		width: 100vw;
		height: 100vh;
		display: flex;
		flex-flow: column nowrap;
		align-items: center;
		justify-content: center;
		position: relative;
		background-color: rgb(253, 228, 232);
	
	
	}
	
	.hero{
		position: relative;
	}
	.herotext{
		font-family: 'Allura', cursive;
		font-size: 94px;
	}
	.subherotext{
	   /*  font-family: 'Fauna One', serif; */
		position: absolute;
		left: 53px;
		top: 87px
	}

	h3{
		font-size: 18px;
	}
	
	
	
	
	.skoleoppgaver{
		
		width: 100px;
		height: 250px;
		margin: auto;
		position: relative; 
		top: 80px;
	}
	
	.circle{
		
		object-fit: cover;
		border-radius: 100%;
		box-shadow: 5px 10px 10px grey;
	}
	
	.center{
		position: absolute;
		top: -35px;
		left: -45px;
		z-index: 4;
		width: 220px;
		height: 220px;
	}.right1{
		position: absolute;
		top: 110px;
		left: 80px;
		z-index: 3;
		width: 200px;
		height: 200px;
	}.left1{
		position: absolute;
		top: 70px;
		right: 80px;
		z-index: 2;
		width: 200px;
		height: 200px;
	}.left2{
		position: absolute;
		top: 20px;
		right: 250px;
		z-index: 1;
		width: 150px;
		height: 150px;
	}.right2{
		position: absolute;
		top: 40px;
		right: -287px;
		z-index: 1;
		width: 150px;
		height: 150px;
	}.right3{
		position: absolute;
		top: 70px;
		right: -380px;
		z-index: 1;
		width: 100px;
		height: 100px;
	}.left3{
		position: absolute;
		top: 100px;
		right: 380px;
		z-index: 1;
		width: 100px;
		height: 100px;
	}.hide{
		display: none;
	}
	
	
	
	</style>
	
	