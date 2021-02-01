<script>
  export let type;
</script>

<div class="flex-col flex justify-between items-center h-1/3 bg-red-300">
  <div class="flex flex-row mx-2.5">
    <input type="checkbox" value="tv" id="tv" bind:group={type} /><label
      for="tv"
      class="text-lg text-white ">TV</label
    >
  </div>
  <div class="flex flex-row mx-2.5">
    <input type="checkbox" value="ova" id="ova" bind:group={type} /><label
      for="ova"
      class="text-lg text-white">OVA</label
    >
  </div>
  <div class="flex flex-row mx-2.5">
    <input type="checkbox" value="movie" id="movie" bind:group={type} /><label
      for="movie"
      class="text-lg text-white">Movies</label
    >
  </div>
  <div class="flex flex-row mx-2.5">
    <input
      type="checkbox"
      value="special"
      id="special"
      bind:group={type}
    /><label for="special" class="text-lg text-white">Specials</label>
  </div>
  <div class="flex flex-row mx-2.5">
    <input type="checkbox" value="ona" id="ona" bind:group={type} /><label
      for="ona"
      class="text-lg text-white">ONA</label
    >
  </div>
</div>
