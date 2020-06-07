<script>
import Trending from "./Trending.svelte";
import Upcoming from "./Upcoming.svelte";
import Footer from "./Footer.svelte";
</script>


<style>
#banner{
    color: #000;
    height: 400px;
    width: 100%;
    }

#banner .banner-title h1{
    margin-top: 5%;
    color: #333;
    font-weight: bold;
    font-size: 3em;
}

#banner .banner-title p{
    color: #333;
    font-size: 1.5em;
}

    .btn{
        font-weight: bold;
        font-size: 1.2em;
        text-transform: capitalize;
    }

    #banner img{
        width: 50%;
        margin: 10% auto;
    }

#blue-section{
    background: blue;
    width: 100%;
    height: 100px;
    padding: 5px; 
}

#Trending{
    color: #fff;
    font-weight: bold;
    background-color: #000;
}

#Upcoming{
    height: 400px;
    width: 100%;
    color: #333;
}

footer{
    margin-top: 5%;
}

</style>

<section id="banner" style="background:url('images/background.jpg')">
    <div class="container">
        <div class="row">
            <div class="col-6">
                <div class="banner-title">
                    <h1>Discover Upcoming Movies Now</h1>
                    <p>Movie Insider tracks future Hollywood films through all stages</p>
                </div>
                
                <button class="btn btn-lg btn-success">In Production →</button>
                <button class="btn btn-lg btn-warning">In Development →</button>
            </div>
            <div class="col-6" style="margin: 0auto">
                <img src="images/play-icon.png" alt="image">
            </div>
        </div>
    </div>
</section>
 <div style="background-color: blue;">
    <div class="container">

      <!-- Grid row-->
      <div class="row py-4 d-flex align-items-center">


         <!-- Grid column -->
        <div class="col-md-6 col-lg-5 text-md-right">

            <h6 style="font-weight: bold; text-align: left; font-size: .9em; color: yellow;">Upcoming films by title, studio, plot or person.</h6>
            <h5 style="font-weight: bold; text-align: left; line-height: 1.5em; color: white;">Find the new movie you heard about!</h5>
        </div>
        <!-- Grid column -->
            
        <!-- Grid column -->
        <div class="col-md-6 col-lg-6 text-center text-md-left mb-4 mb-md-0">
          <!-- Form -->
           <div class="input-group mb-3">
                <input type="text" class="form-control" placeholder="Try Avatar or Marvel" aria-label="Recipient's username"
                    aria-describedby="button-addon2">
                <div class="input-group-append">
                    <button class="btn btn-md btn-warning m-0 px-3 py-2 z-depth-0 waves-effect" type="button" id="button-addon2"><i class="fa fa-search" style="color: black"></i></button>
                </div>
            </div>
            <!-- Form -->
        </div>
        <!-- Grid column -->

       

      </div>
      <!-- Grid row-->

    </div>
</div>



<section id="Trending" class="pt-2 pb-2 pr-5 pl-5">
    <Trending/>
</section>

<section id="Upcoming" class="mt-5 pt-3">
    <Upcoming/>
</section>

<footer>
    <Footer/>
</footer>