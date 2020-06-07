<script>

    import{ onMount } from "svelte";

    import axios from "axios";
    import truncateString from "../helpers/truncate.js";


;

    let output = [];

    function newsUpdate(){
          output = new Date();
    }
    function moviesPoster(){
          output = new Date();
    }

    function moviesInProduction(){
          output = new Date();
    }
    function casting(){
          output = new Date();
    }

    function releaseDates(){
          output = new Date();
    }
    function mpaaRatings(){
          output = new Date();
    }
    function moviesPhoto(){
          output = new Date();
    }


     let upcomingMovies = [];
  const url =
    "https://api.themoviedb.org/3/trending/movie/week?api_key=28704fdf06d73773abebe62251f27700";

  (async function() {
    try {
      const res = await axios.get(url);

      upcomingMovies = res.data.results;
    } catch (error) {
      console.error(error);
    }
  })();


  console.log("hello Muhydeen");
</script>

<style>
    .button{
        background: inherit;
        padding: 10px;
        width: 40%;
        text-align: left;
    }

    .btn-span{
        margin-right: 5%;
    }

    .card{
    width: 10%;
    max-width: 1%;
  }

  .card-title{
    border-top: 5px solid yellow;
  }
</style>


<div class="container">
    <div class="row">    
        <div class="col-6">
                <h5 style="font-weight: bold;">Movie News & Updates</h5>

                <div >
                    <ul class="">
                    {#each upcomingMovies.splice(0, 5)
                     as movie (movie.id)}
                    <span class="">
                        <p >{movie.title}</p> 
                    </span>
                    {/each}
                    </ul>
                </div>

                
        </div>
        <div class="col-6">
            <h6 style="font-weight: bold;" class="pb-2">Updates by Category</h6>
            <div>
                <div>
                    <span class="btn-span">
                        <button on:click = {newsUpdate} type="button" class="button"><i class="fa fa-newspaper .fa-fw"></i> News & Updates</button>
                    </span>
                    <span class="btn-span">
                        <button  on:click = {moviesPoster} type="button" class="button"><i class="fas fa-file-image"></i> Movies Posters</button>
                    </span>  
                </div>
                <div>
                    <span class="btn-span">
                        <button on:click = {moviesInProduction} type="button" class="button"><i class="fas fa-film .fa-fw"></i> Movies in Production</button>
                    </span>
                    <span class="btn-span">
                        <button on:click = {casting} type="button" class="button"><i class="fas fa-user-plus"></i> Casting</button>
                    </span>  
                </div>
                <div>
                    <span class="btn-span">
                        <button on:click = {releaseDates} type="button" class="button"><i class="far fa-calendar"></i> Release Dates</button>
                    </span>
                    <span class="btn-span">
                        <button on:click = {mpaaRatings} type="button" class="button"><i class="fas fa-info-circle"></i> MPAA Ratings</button>
                    </span>  
                </div>
                <div>
                    <span class="btn-span">
                        <button on:click = {moviesPhoto} type="button" class="button"><i class="fas fa-camera fa-fw"></i>Movies Photos</button>
                    </span>
                </div>
                
            </div>
            <div>
                <h5 style="font-weight: bold;" class="pt-3 pb-5">In Case You Missed It</h5>
                <div>{output}</div>
                <button>See Photos</button>
            </div>
            
        </div>
    </div>
</div>