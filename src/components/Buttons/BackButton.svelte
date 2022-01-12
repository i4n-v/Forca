<script>
  import { link } from "svelte-routing";
  import { LeftArrow } from "../";

  export let style = '';
  export let href = '';
</script>

<a {href} use:link class="back-button" style={style}>
  <LeftArrow />
  <span>Voltar</span>
</a>

<style>
  .back-button {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 6rem;
    height: 3rem;
    background: var(--colorTwo);
    border-radius: .5rem;
    border: .1rem solid var(--colorOne);
    cursor: pointer;
    transition: .32s ease-in-out;
    color: #fff ;
    padding: .0rem .8rem;
    text-decoration: none;
  }

  .back-button:hover {
    background: #fff;
    box-shadow: 0 0 .5rem .4rem var(--colorThree);
    color: var(--colorOne);
  }

  .back-button:hover > svg > * {
    stroke: var(--colorOne);
  }

  .back-button > svg {
    width: 30%;
    height: 30%;
  }

  .back-button > span {
    font-size: 1rem;
  }
</style>
