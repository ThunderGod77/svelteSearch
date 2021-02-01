<script>
  import Axios from "axios";

  import Name from "./Components/Name.svelte";
  import TOption from "./Components/TOption.svelte";
  import RatedFor from "./Components/RatedFor.svelte";
  import SubmitB from "./Components/SubmitB.svelte";
  import ShowAnime from "./Components/ShowAnime.svelte";
  import Pagination from "./Components/Pagination.svelte";

  let nameS = "";
  let type = [];
  let rated = "";
  let response = [];
  let animeList = [];
  let show = false;

  let start;
  let end;
  let page = 1;
  let pageNum = 1;
  $: start = (page - 1) * 4;
  $: end = page * 4;

  const sumbitSearch = async () => {
    show = false;
    let url = "https://api.jikan.moe/v3/search/anime";
    let params = {};
    params.limit = 40;
    if (nameS === "") {
      alert("Please enter search query.");
    } else {
      params.q = nameS;
    }
    if (type.length !== 0) {
      if (type.length === 1) {
        params.type = type[0];
      } else {
        params.type = type.reduce((a, b) => `${a}/${b}`);
      }
    }
    if (rated !== "") {
      params.rated = rated;
    }

    // const options = {
    //   method: "GET",
    // };
    response = await Axios.request({
      url: url,
      params: params,
      method: "GET",
    });
    animeList = response.data.results;
    pageNum = Math.floor(animeList.length / 4);

    show = true;
  };
  const goPrev = () => {
    if (page === 1) {
    } else {
      page = page - 1;
    }
  };
  const goNe = () => {
    if (page >= pageNum) {
    } else {
      page = page + 1;
    }
  };
  //
</script>

<div class="flex flex-col md:flex-row h-full">
  <div class="bg-green-200 w-full md:w-1/2  h-full ">
    <div
      class="bg-green-200 border-black   w-full md:w-2/4 h-3/4 md:h-3/4    mx-auto mt-11 mb-11 md:mb-24 md:mt-24 border-4 flex-col flex items-stretch"
    >
      <div class="w-full bg-green-400 border-b-4 border-white h-1/6">
        <p class="text-5xl text-white font-bold font-mono mt-8">
          Search by name:
        </p>
      </div>
      <div
        class="w-full bg-red-300  p-0.5 flex-col flex justify-center items-center h-5/6 "
      >
        <Name bind:nameS />
        <TOption bind:rated />
        <RatedFor bind:type />
        <SubmitB on:submit={sumbitSearch} />
      </div>
    </div>
  </div>
  <div class="bg-blue-200 w-full md:w-1/2">
    <ShowAnime bind:animeList bind:start bind:end />
    <Pagination {show} bind:pageNum bind:page on:prev={goPrev} on:next={goNe} />
  </div>
</div>
