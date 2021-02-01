<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  const submit = () => {
    dispatch("submit", {});
  };
</script>

<button
  class="bg-red-300 border-white text-white py-3 px-6 m-2.5 font-mono font-bold text-3xl hover:bg-white hover:text-red-500"
  on:click={submit}>Search</button
>
