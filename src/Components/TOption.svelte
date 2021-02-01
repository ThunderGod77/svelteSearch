<script>
  export let rated;
</script>

<div class="flex-row flex justify-between items-center h-1/6 bg-red-300">
  <div class="flex flex-row mx-2.5">
    <input type="radio" value="g" id="g" bind:group={rated} /><label
      for="g"
      class="text-lg text-white ">For all ages</label
    >
  </div>
  <div class="flex flex-row mx-2.5">
    <input type="radio" value="pg" id="pg" bind:group={rated} /><label
      for="pg"
      class="text-lg text-white">Children</label
    >
  </div>
  <div class="flex flex-row mx-2.5">
    <input type="radio" value="pg13" id="pg13" bind:group={rated} /><label
      for="pg13"
      class="text-lg text-white">Teens</label
    >
  </div>
  <div class="flex flex-row mx-2.5">
    <input type="radio" value="r17" id="r17" bind:group={rated} /><label
      for="r17"
      class="text-lg text-white">17+</label
    >
  </div>
</div>
