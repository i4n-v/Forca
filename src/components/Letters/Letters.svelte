<script>
  export let letters = [];
  export let selected = [];

  function verifyInSelected(letter, selected) {
    if(selected.includes(letter)) {
      return letter;
    } else {
      return '';
    }
  }
</script>

<div class="letters">
  {#each letters as letter}
    <span>{verifyInSelected(letter, selected)}</span>
  {/each}
</div>

<style>
  .letters {
    width: 100%;
    max-width: 30rem;
    padding: 1rem;
    margin: 2.2rem auto;
    display: flex;
    justify-content: center;
    align-items: flex-end;
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
    height: 2.75rem;
  }
</style>
