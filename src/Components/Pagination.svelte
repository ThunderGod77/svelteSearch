<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  export let show;
  export let pageNum;
  export let page;
  let activate = "bg-green-300 text-white";
  let deactivateHover = "";
  let deactivate = "bg-green-200 text-gray-400";
  let activateHover = " hover:bg-white hover:text-green-400";

  const goPrevious = () => {
    dispatch("prev");
  };
  const goNext = () => {
    dispatch("next");
  };
</script>

{#if show}
  <div class="flex flex-row justify-between mt-4">
    <button
      class="text-3xl {page === 1
        ? deactivate
        : activate} p-3 border-2 border-white rounded-2xl ml-20 {page === 1
        ? deactivateHover
        : activateHover} "
      on:click={goPrevious}>Previous</button
    >
    <button
      class="text-3xl {page === pageNum
        ? deactivate
        : activate} p-3 border-2 border-white rounded-2xl mr-20 {page ===
      pageNum
        ? deactivate
        : activate}"
      on:click={goNext}>Next</button
    >
  </div>
{/if}
