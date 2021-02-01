<script>
  export let nameS;
</script>

<div class="flex-row flex justify-center items-center h-1/8 bg-red-300">
  <label for="animeName" class="text-xl text-white">Enter:</label>
  <input
    id="animeName"
    type="text"
    placeholder="enter here"
    class="h-5/6 p-2 m-0.5"
    bind:value={nameS}
  />
</div>
