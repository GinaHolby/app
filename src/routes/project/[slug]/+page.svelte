<script>
  export let data;

  import "./project.css";

  import Figma from "../../../assets/icons/Figma.svelte";
  import Internet from "../../../assets/icons/Internet.svelte";
  import Notion from "../../../assets/icons/Notion.svelte";

  console.log(data)
</script>

<header>
  <a class="h" href="/">
    <h1 class="herotext">Gina Holby</h1>
    <h3 class="subherotext">UX-designer</h3>
  </a>
</header>

<main>
  {#each data.recipies as project}
    <img class=" coverimage" src={project.cover} alt="" />

    <div class="information">
      <div class="title">
        <h1>
          {project.projectTitle}
        </h1>
      </div>

      <h3>{project.shortProjectDescription}</h3>

      <div class="ikoner">

        <div class="{project.figmalink ? "show" : "hide"}">
          <p>link til Figma:</p>
          <a href={project.figmalink} target="_blank">
            <div class="figma-logo"> <Figma /></div>
          </a>
        </div>

        <div class="{project.nettsidelink ? "show" : "hide"}">
          <p>link til nettside:</p>
          <a href={project.nettsidelink} target="_blank">
            <div class="figma-logo"> <Internet /></div>
          </a>
        </div>
        <div class="{project.notionlink ? "show" : "hide"}">
          <p>link til Notion:</p>
          <a href={project.notionlink} target="_blank">
            <div class="figma-logo"> <Notion /></div>
          </a>
        </div>
        

        
      </div>

      {#if project.information}
      <div class="projectInformation">
        {#each project.information as info}
          {#if info.style === 'normal'}
            <p> {info.children[0].text}</p> 
          {/if}
          {#if info.style === 'h3'}
            <p class="lineBreak"> </p>
            <h3>{info.children[0].text}</h3> 
          {/if}
          {#if info.style === 'h4'}

          <p class="slineBreak"> </p>
            <h4>{info.children[0].text}</h4> 
          {/if}
        {/each} 
      </div>
      {/if}
     
              
              
              <!-- {#if instruction._type === 'block' & instruction.listItem !== 'bullet'}
                <span class="p">{instruction.children[0].text}</span>
              {/if}
              {#if instruction._type === 'image'}  
              <div class="instructionImages oneImage">
                <img class="instructionImage" 
                     src="{urlFor(instruction.asset._ref).url()}" 
                     alt=""
                >
              </div> 
              {/if} -->
             <!--  {#if instruction._type === 'twoImages'}
              <div class="instructionImages twoImages">
                <img class="instructionImage" src="{urlFor(instruction.image1of2.asset._ref).url()}" alt="">
                <img class="instructionImage" src="{urlFor(instruction.image2of2.asset._ref).url()}" alt="">
              </div>   
              {/if}
              {#if instruction._type === 'threeImages'} 
                <div class="instructionImages threeImages">
                  <img class="instructionImage threeImage" src="{urlFor(instruction.image1of3.asset._ref).url()}" alt="">
                  <img class="instructionImage threeImage" src="{urlFor(instruction.image2of3.asset._ref).url()}" alt="">
                  <img class="instructionImage threeImage" src="{urlFor(instruction.image3of3.asset._ref).url()}" alt="">
                </div>  
              {/if} -->
    </div>
  {/each}
</main>

<style>
  header {
    display: flex;
    justify-content: center;
    padding: 12px;
    background-color: rgb(253, 228, 232);
    position: fixed;
    width: 100%;
    z-index: 2;
  }
  .h {
    position: relative;
  }
  .herotext {
    font-family: "Allura", cursive;
    font-size: 40px;
  }
  .subherotext {
    /* font-family: "Fauna One", serif; */
    position: absolute;
    left: 30px;
    top: 33px;
    font-size: 12px;
    width: 100%;
  }
  .projectInformation{
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }
  
  
  
  .lineBreak{
    height: 0.5rem;
  }
  .slineBreak{
    height: 0.01rem;
  }

  .hide{
    display: none;
  }
  .show{
    display: flex;
  }
</style>
<link rel="preconnect" href="https://fonts.googleapis.com"> 
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin> 
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Montserrat:wght@100&family=Quicksand:wght@300;700&display=swap" rel="stylesheet">
