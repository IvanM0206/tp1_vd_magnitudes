<script>

  let numbers = [12.3, 30.75, 41, 76.26, 92.25, 123];

</script>


<div class="row-container">
  <h1>CARGAS DE BATERIA</h1>
  {#each numbers as number}
  {#if number == 123}
    <div class="row-wrapper">
      <div class="row" style="width: {number}px; border-top-right-radius: 7%; border-bottom-right-radius: 7%;">
      </div>
      <img class="battery-mask" src="./images/Vector.svg" alt="">
      <p>{100*number/123}%</p>
    </div>
  {:else if number == 12.3}
  <div class="row-wrapper">
    <div class="row" style="width: {number}px; background-color: red;">
    </div>
    <img class="battery-mask" src="./images/Vector.svg" alt="">    
    <p>{100*number/123}%</p>
  </div>
  {:else if number == 30.75}
  <div class="row-wrapper">
    <div class="row" style="width: {number}px; background-color: yellow;">
    </div>
    <img class="battery-mask" src="./images/Vector.svg" alt=""> 
    <p>{100*number/123}%</p>  
  </div>
  {:else}
  <div class="row-wrapper">
    <div class="row" style="width: {number}px;">
    </div>
    <img class="battery-mask" src="./images/Vector.svg" alt="">
    <p>{Math.round(100*(number/123))}%</p>   
  </div>
  {/if}
  {/each}
</div>

<style>
  :global(body){
    background-color: #B6B6B6;
  }
  h1{
    left: 30%;
    top: 0;
    position: fixed;
    color: #000;
  }
  p{
    position: absolute;
    font-size: 25px;
  }
  .row{
    position: absolute;
    bottom: 27px;
    left: 33px;
    height: 60px;
    border-top-left-radius: 7%;
    border-bottom-left-radius: 7%;
    background-color: white;
  }
  .row-container{
    display: flex;
  }
  .row-wrapper{
    position: relative;
    width: 200px;
    display: flex;
    justify-content: center;
  }
  .battery-mask
  {
    position: absolute;
    z-index: 1;
    bottom: 0;

  }
</style>
