<script>

  let numbers = [10, 25, 33, 62, 75, 100];

</script>


<div class="row-container">
  <h1>CARGAS DE BATERIA</h1>
  <!--SEPARO EN CUATRO CASOS PORQUE CAMBIO EL COLOR (PARA EL 10% Y EL 25%) Y EL BORDE DE LA CARGA (PARA EL 100%)-->
  {#each numbers as number}
  <!--Borde más redondeado-->
  {#if number == 100}
    <div class="row-wrapper">
      <div class="row" style="width: {number*1.23}px; border-top-right-radius: 7%; border-bottom-right-radius: 7%;">
      </div>
      <img class="battery-mask" src="./images/Vector.svg" alt="">
      <p>{number}%</p>
    </div>
  <!--Color de bateria: rojo-->
  {:else if number == 10}
  <div class="row-wrapper">
    <div class="row" style="width: {number*1.23}px; background-color: red;">
    </div>
    <img class="battery-mask" src="./images/Vector.svg" alt="">    
    <p>{number}%</p>
  </div>
  <!--Color de bateria: amarillo-->
  {:else if number == 25}
  <div class="row-wrapper">
    <div class="row" style="width: {number*1.23}px; background-color: yellow;">
    </div>
    <img class="battery-mask" src="./images/Vector.svg" alt=""> 
    <p>{number}%</p>  
  </div>
  <!--Color de bateria: blanco-->
  {:else}
  <div class="row-wrapper">
    <div class="row" style="width: {number*1.23}px;">
    </div>
    <img class="battery-mask" src="./images/Vector.svg" alt="">
    <p>{number}%</p>   
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
