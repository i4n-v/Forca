<script>
  import { link } from "svelte-routing";

  export let href = "";
  export let onClick = () => {};
</script>

<a {href} use:link on:click={onClick} class="btn-modal">
  <slot />
</a>

<style>
  .btn-modal {
    padding: 0.8rem 0.4rem;
    width: 100vw;
    max-width: 13rem;
    border-radius: 0.6rem;
    border: 0.1rem solid var(--colorOne);
    background-color: var(--colorTwo);
    color: #ffff;
    font: bold 1rem var(--nunito);
    text-decoration: none;
    text-align: center;
    overflow: hidden;
    transition: 0.3s ease-in-out;
  }

  .btn-modal:hover {
    background: #fff;
    box-shadow: 0 0 0.5rem 0.4rem var(--colorThree);
    color: var(--colorOne);
  }
</style>
