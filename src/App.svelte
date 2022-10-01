<script>

  import  Character from './libs/Character.svelte'

  let characters = []
  let page = 1

  async function loadCharacters() {
    const  response = await fetch('https://rickandmortyapi.com/api/character?page=' + page)
    const data = await response.json()
    characters = data.results;
  }
  loadCharacters()

  function nextPage() {
    page++;
  loadCharacters()

  }

  function previousPages(){
    page--;
  loadCharacters()

  }
 
</script>


<h1 class="title">Ricky and Morty</h1>



<div class="container">
  
  <div class="btns">
     <button class="btn" on:click={previousPages} disabled={page===1}>Previous</button>
     <button class="btn" on:click={nextPage}>Next</button>
  
  </div>
  <div class="grid">
    {#each characters as character}
    
      <Character character = {character}></Character>
    {/each}
  </div>

</div>