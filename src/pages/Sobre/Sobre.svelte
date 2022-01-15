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
        style="position: absolute; top: 3.4rem; right: 7.63rem;"
      />
    </div>
    <div id="cards-container">
      <div>
        <AboutCard
          author="Victor Guilherme"
          instagram={{
            src: "https://www.instagram.com/vict0r_guilhermee/",
            name: "vict0r",
          }}
          github={{
            src: "https://github.com/Vict0r-Guilherme",
            name: "Vict0r",
          }}
          linkedin={{
            src: "https://www.linkedin.com/in/victor-guilherme-455951215",
            name: "vict0r",
          }}
          img="/assets/img/git-blue.png"
        />
        <AboutCard
          author="Pedro Vinicius"
          instagram={{
            src: "#https://www.instagram.com/Pedrovinicius.1/",
            name: "Pedro",
          }}
          github={{ src: "https://github.com/PdrVinicius", name: "Pedro" }}
          linkedin={{
            src: "https://www.linkedin.com/mwlite/in/pedro-vin%C3%ADcius-lopes-xavier-595b98198",
            name: "Pedro",
          }}
          img="/assets/img/git-brown.png"
        />
      </div>
      <div id="center-card">
        <AboutCard
          author="Ian Vinícius"
          instagram={{ src: "https://www.instagram.com/i4n_v/", name: "i4n_v" }}
          github={{ src: "https://github.com/i4n-v", name: "i4n-v" }}
          linkedin={{
            src: "https://www.linkedin.com/in/i4n-v/",
            name: "i4n-v",
          }}
          img="/assets/img/git-green.png"
        />
      </div>
      <div>
        <AboutCard
          author="Polyana Giselle"
          instagram={{
            src: "https://www.instagram.com/poly_gih/",
            name: "poly_gih",
          }}
          github={{ src: "https://github.com/Polyalves2", name: "poly" }}
          linkedin={{ src: "#", name: "# _ #" }}
          img="/assets/img/git-pink.png"
        />
        <AboutCard
          author="Victor Antônio"
          instagram={{
            src: "https://www.instagram.com/victor_lemos2020/",
            name: "victor",
          }}
          github={{ src: "https://github.com/victor16042002", name: "victor" }}
          linkedin={{ src: "#", name: "# _ #" }}
          img="/assets/img/git-purple.png"
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
    gap: 0.5rem;
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
    #cards-container {
      flex-direction: column;
      align-items: center;
    }

    #cards-container > div {
      gap: 0.5rem;
    }
  }
</style>
