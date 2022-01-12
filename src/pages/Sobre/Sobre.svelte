<script>
  import { BackButton, AboutCard } from "../../components";
</script>

<svelte:head>
  <title>Forca | Sobre</title>
</svelte:head>
<main class="wrapper">
  <div id="about-container">
    <div>
      <h1 class="title">SOBRE</h1>
      <BackButton
        href="/"
        style="position: absolute; top: .5rem; right: .5rem;"
      />
    </div>
    <div id="cards-container">
      <div>
        <AboutCard
          author="teste"
          instagram={{ src: "#", name: "teste" }}
          github={{ src: "#", name: "teste" }}
          linkedin={{ src: "#", name: "teste" }}
        />
        <AboutCard
          author="teste"
          instagram={{ src: "#", name: "teste" }}
          github={{ src: "#", name: "teste" }}
          linkedin={{ src: "#", name: "teste" }}
        />
      </div>
      <div id="center-card">
        <AboutCard
          author="teste"
          instagram={{ src: "#", name: "teste" }}
          github={{ src: "#", name: "teste" }}
          linkedin={{ src: "#", name: "teste" }}
        />
      </div>
      <div>
        <AboutCard
          author="teste"
          instagram={{ src: "#", name: "teste" }}
          github={{ src: "#", name: "teste" }}
          linkedin={{ src: "#", name: "teste" }}
        />
        <AboutCard
          author="teste"
          instagram={{ src: "#", name: "teste" }}
          github={{ src: "#", name: "teste" }}
          linkedin={{ src: "#", name: "teste" }}
        />
      </div>
    </div>
  </div>
</main>

<style>
  #about-container {
    width: 100%;
    min-height: 42rem;
    max-width: 80rem;
    padding: 1rem;
  }

  #cards-container {
    display: flex;
    justify-content: space-between;
    margin-top: 1.8rem;
    gap: .5rem;
  }

  #cards-container > div {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    gap: 5rem;
    width: 100%;
  }

  #center-card {
    display: flex;
    justify-content: center !important;
    align-items: center;
  }

  @media (max-width: 55rem) {
    #cards-container{
      flex-direction: column;
      align-items: center;
    }

    #cards-container > div {
      gap: .5rem;
    }
  }
</style>
