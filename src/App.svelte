<script>
  let cupsOfCoffee = 1;
  let ratio;

  let leftRatio = 1;
  let rightRatio = 16;

  $: ratio = rightRatio / leftRatio;
  $: gramsOfCoffee = Math.round(millilitersOfWater / ratio)
  $: millilitersOfWater = Math.round(cupsOfCoffee * 236.6);
</script>

<main>
  <h1>Coffee Ratio Calculator</h1>

  <label for="cups"><strong>Cups of Coffee</strong></label>
  <input id="cups" type="text" bind:value={cupsOfCoffee} size="2">

  <label for="ratio"><strong>Coffee Ratio</strong></label>
  <input id="left_ratio" type="text" bind:value={leftRatio} size="2"> :
  <input id="left_ratio" type="text" bind:value={rightRatio} size="2">


  <div id="results">
    <div id="card">
      <h3>Grams of Coffee</h3>
      <h2>{gramsOfCoffee}g</h2>
      <!-- <input type="text" size="6" bind:value={gramsOfCoffee} on:keydown={gramsEdited}> g -->
    </div>

    <div id="card">
      <h3>Milliliters of Water</h3>
      <!-- <input type="text" size="6" bind:value={millilitersOfWater} on:keydown={mlEdited}> mL -->
      <h2>{millilitersOfWater}mL</h2>
    </div>
  </div>

</main>

<footer>
  <p>Created by <a href="https://typicel.me">enzo</a>. View on <a href="https://github.com/typicel/coffee-calculator">Github</a></p>
</footer>

<style>
  #results {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    padding-top: 1rem;
  }

  #card {
    max-width: 18rem;
    padding: 10px;
    margin: 1rem;
    border: 1px solid black;
    border-radius: 10px;
    background-color: #634832;
  }
  
  #card > h3,
  #card > h2 {
    margin: 0;
  }

  footer {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    color: var(--text-color);
    text-align: center;
    padding: 5px;
  }

</style>
