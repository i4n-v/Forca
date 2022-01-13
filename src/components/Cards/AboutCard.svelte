<script>
  import {Instagram, Github, Linkedin} from "../";

  export let author = "";
  export let img = "";
  export let instagram = {};
  export let github = {};
  export let linkedin = {};
</script>

<div class="card">
  <div class="author-container">
    <div class="img">
      <img src={img} alt="Desenvolvedor do jogo" />
    </div>
    <p>{author}</p>
  </div>
  <div class="medias">
    <div>
      <Instagram width="1.5rem" height="1.5rem" />
      <a href={instagram.src || ''} target="_blank">@{instagram.name || ''}</a>
    </div>
    <div>
      <Github width="1.5rem" height="1.5rem" />
      <a href={github.src || ''} target="_blank">@{github.name || ''}</a>
    </div>
    <div>
      <Linkedin width="1.5rem" height="1.5rem" />
      <a href={linkedin.src} target="_blank">@{linkedin.name || ''}</a>
    </div>
  </div>
</div>

<style>
  .card {
    width: 100%;
    max-width: 19rem;
    min-height: 14rem;
    border: 0.2rem solid var(--colorOne);
    border-radius: 0.8rem;
    background-color: var(--colorTwo);
    padding: .8rem;
  }

  .author-container{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: .5rem;
  }

  .author-container > p {
    font-size: 1.2rem;
    color: #fff;
  }

  .img {
    width: 6rem;
    height: 6rem;
    background-color: var(--colorFour);
    border-radius: 100%;
    border: .2rem solid var(--colorOne);
    overflow: hidden;
  }

  .img > img {
    width: 100%;
    height: 100%;
  }

  .medias {
    display: flex;
    justify-content: space-between;
    margin-top: 1.5rem;
  }

  .medias > div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: .1rem;
    transition: .3s ease-in-out;
  }

  .medias > div:hover > a {  
    color: var(--colorOne);
  }

  :global(.medias > div:hover > *) {  
    fill: var(--colorOne);
  }

  .medias, a {
    text-decoration: none;
    color: #fff;
    font-size: .9rem;
  }
</style>
