<script>
  import { SelectedLetters, BackButton, PlayersCard } from "../../components";
</script>

<svelte:head>
  <title>Forca | Jogando</title>
</svelte:head>
<main class="wrapper">
  <div class="info-container shadow-container">
    <SelectedLetters title="Letras escolhidas" letters={['a', 'b', 'c']} />
    <BackButton href="/" style="position: absolute; top: 2rem; right: .7rem;" />
    <PlayersCard players={[{name: 'player 1', points: 2, color: '#F04444'}, {name: 'player 2', points: 3, color: '#4489F0'}]} />
  </div>
</main>

<style>
	.info-container {
    min-height: 34.7rem;
    position: relative;
  }
</style>