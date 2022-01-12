<script>
  export let title = "";
  export let img = "";
</script>

<div class="info-content anime-left">
  <h2 class="title-ifn">{title}</h2>
  <div>
    <p>
      <slot />
    </p>
    <div class="game-example">
      <img src={img} alt="Examplo do jogo da forca" />
    </div>
  </div>
</div>

<style>
  .info-content {
    width: 90%;
    min-height: 20rem;
    margin: 2rem auto 0rem auto;
  }

  .info-content > div {
    display: flex;
    justify-content: space-between;
    gap: 2rem;
  }

  h2 {
    margin-left: 0.3rem;
    max-width: 35rem;
  }

  p {
    max-width: 35rem;
    text-align: justify;
    font-size: 1.3rem;
    color: var(--colorFive);
  }

  .game-example {
    max-height: 15rem;
    max-width: 30rem;
    background-color: #fff;
    border-radius: 0.8rem;
    border: 0.2rem solid var(--colorOne);
    overflow: hidden;
    flex-shrink: 0;
  }

  img {
    width: 100%;
    height: 100%;
  }

  @media (max-width: 70rem) {
    .info-content > div {
      flex-direction: column;
    }

    p, h2, .game-example {
      margin-left: auto;
      margin-right: auto;
    }
  }
</style>
