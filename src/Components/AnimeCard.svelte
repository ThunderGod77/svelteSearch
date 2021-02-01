<script>
  export let name;
  export let imageURL;
  export let episodes;
  export let score;
  export let synopsis;
</script>

<div class="bg-red-200 flex flex-col" style="height:350px;">
  <div class="bg-green-300 w-full h-1/6">
    <h1
      class="font-mono text-xl h-full bg-yellow-400 font-medium text-white pt-1 "
    >
      {name}
    </h1>
  </div>
  <div class="h-5/6 flex flex-row w-full bg-green-200">
    <div class="h-full ">
      <img src={imageURL} alt="anime cover" class="h-full" />
    </div>
    <div class="bg-blue-200 w-3/4 border-white border-2 text-white rounded-xl">
      <p>Episodes: {episodes}</p>
      <p>Score :{score}</p>
      <p>Synopsis : {synopsis}</p>
    </div>
  </div>
</div>
