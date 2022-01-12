<script>
  import { Logo, ButtonMenu } from '../../components';
</script>

<svelte:head>
  <title>Forca | Menu</title>
</svelte:head>
<main class="wrapper">
  <div id="container-menu">
    <Logo />
    <nav class="menu">
      <ButtonMenu href="/jogar" >JOGAR</ButtonMenu>
      <ButtonMenu href="/como_jogar" >COMO JOGAR</ButtonMenu>
      <ButtonMenu href="/sobre" >SOBRE</ButtonMenu>
    </nav>
  </div>
</main>

<style>
    #container-menu {
      max-width: 23rem;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .menu {
      margin-top: 1rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: .8rem;
    }
</style>