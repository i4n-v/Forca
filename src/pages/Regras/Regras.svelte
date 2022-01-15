<script>
  import { InfoContainer, ArrowButton, BackButton } from "../../components";

  let slide = 0;

  function nextSlide() {
    if (slide < 1) {
      slide += 1;
    }
  }

  function backSlide() {
    if (slide > 0) {
      slide -= 1;
    }
  }
</script>

<svelte:head>
  <title>Forca | Como Jogar</title>
</svelte:head>
<main class="wrapper">
  <section class="info-container shadow-container">
    <div>
      <h1 class="title">COMO JOGAR ?</h1>
      <BackButton href="/" style="position: absolute; top: .7rem; right: .7rem;" />
    </div>
    {#if slide === 0}
      <InfoContainer title="Objetivo do jogo" img="/assets/img/game.png">
        O objetivo deste jogo é descobrir uma palavra adivinhando as letras que
        ela possui. A cada rodada, os jogadores irão escolher uma letra que
        suspeitem fazer parte da palavra. Caso a palavra contenha esta letra,
        será mostrado em que posição(ões) ela está. Entretanto, caso esta letra
        não exista na palavra, será desenhada uma parte do corpo do boneco na
        forca. Se todas as 6 partes do corpo do boneco estiverem desenhadas, a
        rodada será finalizada.
      </InfoContainer>
    {:else if slide === 1}
      <InfoContainer title="Condição de vitória" img="/assets/img/victory.png">
        A vitória de um jogador é determinada pela sua pontuação ao decorrer das
        3 rodadas do jogo. A cada rodada os jogadores tentarão acertar a palavra
        determinada, escolhendo letra por letra, o jogador que acertar ganhará a
        rodada, que somará mais um ponto no total de sua pontuação.
      </InfoContainer>
    {/if}
    <div class="button-container">
      <ArrowButton btnType="back" onClick={backSlide} disabled={slide < 1} />
      <ArrowButton onClick={nextSlide} disabled={slide >= 1} />
    </div>
  </section>
</main>

<style>
  .info-container {
    min-height: 33rem;
    position: relative;
  }

  .button-container {
    width: 90%;
    margin: 4rem auto auto auto;
    display: flex;
    justify-content: space-between;
  }
</style>
