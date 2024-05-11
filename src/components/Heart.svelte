<script>
  let clicked = 0;

  function handleClick() {
    clicked += 1;
  }
</script>

<div class="heart-container">
  <button type="button" on:click={handleClick}> ❤️ </button>
  <p class="counter">{clicked}</p>
</div>

<style>
  .heart-container {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 20px;
  }

  button {
    font-size: 24px;
    padding: 10px 20px;
    border: none;
    background-color: transparent;
    cursor: pointer;
    transition: transform 0.2s;
  }

  button:hover {
    transform: scale(1.1);
  }

  .counter {
    font-size: 18px;
    margin-left: 5px;
    color: blue;
  }
</style>
