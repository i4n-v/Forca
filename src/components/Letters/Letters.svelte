<script>
  export let letters = [];
</script>

<div class="letters">
  {#each letters as letter}
    <span>{letter}</span>
  {/each}
</div>

<style>
  .letters {
    width: 100%;
    max-width: 30rem;
    padding: 1rem;
    margin: 2rem auto;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: .8rem;
    flex-wrap: wrap;
  }

  .letters > span {
    width: 4rem;
    border-bottom: .3rem solid var(--colorTwo);
    text-align: center;
    font-size: 1.8rem;
    color: var(--colorFive);
    font-weight: bold;
  }
</style>
