<script>
  export let animeList;
  export let start = 0;
  export let end = 4;
  $: console.log(start);
  $: showList = animeList.slice(start, end);
  
  import AnimeCard from "./AnimeCard.svelte";
</script>

<div class="grid grid-cols-1 md:grid-cols-2" style="height:700px;">
  {#each showList as anime (anime.mal_id)}
    <AnimeCard
      name={anime.title}
      imageURL={anime.image_url}
      score={anime.score}
      episodes={anime.episodes}
      synopsis={anime.synopsis}
    />
  {/each}
</div>
