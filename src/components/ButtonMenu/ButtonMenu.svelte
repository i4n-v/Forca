<script>
  import { link } from "svelte-routing";

  export let href = "";
</script>

<a {href} use:link class="btn-menu">
  <span />
  <span />
  <span />
  <span />
  <slot />
</a>

<style>
  .btn-menu {
    padding: 1rem 0.4rem;
    width: 100vw;
    max-width: 19rem;
    border-radius: 0.6rem;
    outline: none;
    border: 0.1rem solid var(--colorOne);
    background-color: var(--colorTwo);
    color: #ffff;
    font: bold 1.5rem var(--nunito);
    text-decoration: none;
    text-align: center;
    overflow: hidden;
    transition: 0.2s;
    position: relative;
  }

  .btn-menu:hover {
    color: var(--colorOne);
    background: #fff;
    box-shadow: 0 0 20px var(--colorThree), 0 0 40px var(--colorThree),
      0 0 80px var(--colorThree), 0 0 100px var(--colorThree);
    transition-delay: 1s;
  }

  .btn-menu span {
    position: absolute;
    display: block;
  }
  
  .btn-menu span:nth-child(1) {
    top: 0;
    transform: translateX(-115%);
    width: 100%;
    height: 4px;
    background: linear-gradient(90deg, transparent, var(--colorOne));
  }

  .btn-menu:hover span:nth-child(1) {
    transform: translateX(100%);
    transition: 1s;
  }

  .btn-menu span:nth-child(3) {
    bottom: 0;
    transform: translateX(100%);
    width: 100%;
    height: 4px;
    background: linear-gradient(270deg, transparent, var(--colorOne));
  }

  .btn-menu:hover span:nth-child(3) {
    transform: translateX(-115%);
    transition: 1s 0.5s;
  }

  .btn-menu span:nth-child(2) {
    right: 0;
    transform: translateY(-130%);
    width: 4px;
    height: 100%;
    background: linear-gradient(180deg, transparent, var(--colorOne));
  }

  .btn-menu:hover span:nth-child(2) {
    transform: translateY(100%);
    transition: 1s 0.25s;
  }

  .btn-menu span:nth-child(4) {
    left: 0;
    transform: translateY(100%);
    width: 4px;
    height: 100%;
    background: linear-gradient(360deg, transparent, var(--colorOne));
  }

  .btn-menu:hover span:nth-child(4) {
    transform: translateY(-130%);
    transition: 1s 0.75s;
  }
</style>
