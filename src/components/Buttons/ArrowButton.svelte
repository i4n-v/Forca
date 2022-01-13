<script>
  import { LeftArrow, RightArrow } from "../";

  export let disabled = false;
  export let btnType = 'next';
  export let onClick = () => {};
</script>

<button class='arrow-button' disabled={disabled} on:click={() => onClick()}>
  {#if btnType === 'back'}
    <LeftArrow />
  {:else}
    <RightArrow />
  {/if}
</button>

<style>
  .arrow-button {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 4rem;
    height: 3rem;
    background: var(--colorTwo);
    border-radius: .5rem;
    border: .1rem solid var(--colorOne);
    cursor: pointer;
    transition: .32s ease-in-out;
  }

  .arrow-button:hover {
    background: #fff;
    box-shadow: 0 0 .5rem .4rem var(--colorThree);
  }

  :global(.arrow-button:hover > svg > *) {
    stroke: var(--colorOne);
  }

  :global(.arrow-button > svg) {
    width: 50%;
    height: 50%;
  }
</style>
