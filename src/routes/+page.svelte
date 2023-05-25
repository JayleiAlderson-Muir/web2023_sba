<script>
  const BASE_URL = `https://rickandmortyapi.com/api/character/[1,2,3,4,5,6]`;

  let characters;

  fetch(`${BASE_URL}?json=true`)
    .then((res) => res.json())
    .then((data) => {
      characters = data;
      console.log(characters);
    });
</script>

<div class="grid">
  {#each characters as character}
    <div class="card">
      <div><img class="image" src={character.image} /></div>
      <div class="info">
        <h1 class="name">{character.name}</h1>
        <h3 class="status">
          <div class="dead" />
          {character.status}
        </h3>

        <h3 class="locationLabel">Last known location</h3>
        <h3 class="location">
          <a href="/location">{character.location.name}</a>
        </h3>
      </div>
    </div>
  {/each}
</div>
