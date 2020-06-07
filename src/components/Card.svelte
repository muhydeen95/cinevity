<script>
    export let imgSrc,movieName;
</script>

<style>

  .card{
    margin-top: 10px;
    background: #000;
  }
  
  .card-title{
    border-top: 5px solid yellow;
    font-size: 1.3em;
  }
</style>

      <div class="card">
        <img
          class="card-img-top"
          src={imgSrc}
          alt="Movie poster" />
        <div class="card-body">
          <h4 class="card-title">
            <a>{movieName}</a>
          </h4>
          
        </div>

      </div>
