<script>
  export let title = "";
  export let letters = [];
</script>

<div id="selected-letters">
  <h2 class="title-ifn">{title}</h2>
  <div>
    {#each letters as letter}
      <span>{letter}</span>
    {/each}
  </div>
</div>

<style>
  #selected-letters {
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    left: 2rem;
  }

  #selected-letters > div {
    width: 13rem;
    height: 9rem;
    padding: .5rem;
    background: #fff;
    border-radius: 0.5rem;
    border: 0.2rem solid var(--colorOne);
  }

  #selected-letters > div > span {
    font-size: 1.2rem;
    font-weight: bold;
    color: var(--colorFive);
    margin-left: .5rem;
    display: inline-block;
  }

  .title-ifn {
    font-size: 1.3rem;
  }

  .title-ifn:after {
    width: 1rem;
    height: 1rem;
    position: absolute;
    bottom: -0.2rem;
    left: -0.3rem;
    border-radius: 0.2rem;
  }
</style>
