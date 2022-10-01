<script>
  export let character;
</script>


<div class="character">
  <img src={character.image} alt="">
  <h1>{character.name}</h1>
  <h3>{character.species}</h3>
</div>