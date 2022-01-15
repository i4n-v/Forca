<script>
  export let letter = '';

  export let onClick = () => {};
</script>

<button type="button" class="game-button" on:click={onClick(letter)}>
  {letter}
</button>

<style>
  .game-button {
    padding: .6rem;
    width: 4rem;
    text-align: center;
    color: var(--colorFive);
    background: #fff;
    font-size: 1.3rem;
    border: .1rem solid var(--colorOne);
    border-radius: .5rem;
    transition: .32s ease-in-out;
    cursor: pointer;
  }

  .game-button:hover {
    background: var(--colorTwo);
    box-shadow: 0 0 .5rem .4rem var(--colorThree);
    color: var(--colorOne);
  }
</style>