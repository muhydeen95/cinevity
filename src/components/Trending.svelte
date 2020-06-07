<script>
  import{ onMount } from "svelte";

  import axios from "axios";

  import truncateString from "../helpers/truncate.js";

  import "../../node_modules/@glidejs/glide/dist/css/glide.core.min.css";

  import "../../node_modules/@glidejs/glide/dist/css/glide.theme.min.css";
  
  import Glide from "@glidejs/glide";

  import Card from "./Card.svelte";

  onMount(() =>{
    new Glide(".glide", {
      perView: 6,
      autoplay: 2000,
      gap: 50
    }).mount();
  });

 // onMount(() => {
    //const options ={
      //type: "carousel",
      //startAt: 0,
      //perView:6,
      //gap: 50,
      //autoplay:2000,
      //hoverpause:true
    //}
    //new Glide(".glide", options).mount();
  //});

  

  let trendingMovies = [];
  const url =
    "https://api.themoviedb.org/3/trending/movie/week?api_key=28704fdf06d73773abebe62251f27700";

  (async function() {
    try {
      const res = await axios.get(url);

      trendingMovies = res.data.results;
    } catch (error) {
      console.error(error);
    }
  })();

  console.log("hello Muhydeen");
</script>

<style>
  .card{
    width: 24%;
    max-width: 1%;
  }

  .card-title{
    border-top: 5px solid yellow;
  }
</style>

<div class="row mt-4">
  <div class="col-12">
    <h5>Anticipated Upcoming Movies</h5>
  <div class="glide">
  <div class="glide__track" data-glide-el="track">
    <ul class="glide__slides">
    {#each trendingMovies as movie (movie.id)}
      <li class="glide__slide">
        <Card movieName ={truncateString(movie.title,10)} 
        imgSrc={`https://image.tmdb.org/t/p/original/${movie.poster_path}`}/>
      
      </li>
      {/each}
    </ul>
  </div>
</div> 
</div>
</div>
