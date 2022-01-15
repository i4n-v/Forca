<script>
  import { ButtonModal } from "../";

  export let onClick = () => {};
</script>

<div class="modal">
  <div class="anime-scale">
    <slot name="title" />
    <div>
      <ButtonModal href="/">MENU</ButtonModal>
      <ButtonModal onClick={onClick}>JOGAR NOVAMENTE</ButtonModal>
    </div>
  </div>
</div>

<style>
  .modal {
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.2);
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .modal > div {
    width: 100%;
    max-width: 35rem;
    height: 18rem;
    background-color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 2rem;
    border-radius: 0.5rem;
  }

  .modal > div > div {
    display: flex;
    justify-content: space-between;
    gap: 0.5rem;
  }

  :global(.modal h2) {
    font-size: 1.5rem;
    text-align: center;
  }
</style>
