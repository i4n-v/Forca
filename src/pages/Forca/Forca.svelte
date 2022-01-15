<script>
  import {
    SelectedLetters,
    BackButton,
    PlayersCard,
    ForcaSvg,
    StickmanSvg,
    Letters,
    KeyBoardGame,
    Modal,
  } from "../../components";

  const words = [
    "Amarelo",
    "Amiga",
    "Amor",
    "Ave",
    "Avião",
    "Avó",
    "Balão",
    "Bebê",
    "Bolo",
    "Branco",
    "Cama",
    "Caneca",
    "Celular",
    "Clube",
    "Copo",
    "Doce",
    "Elefante",
    "Escola",
    "Estojo",
    "Faca",
    "Foto",
    "Garfo",
    "Geleia",
    "Girafa",
    "Janela",
    "Limonada",
    "Mae",
    "Meia",
    "Noite",
    "Óculos",
    "ônibus",
    "Ovo",
    "Pai",
    "Pão",
    "Parque",
    "Passarinho",
    "Peixe",
    "Pijama",
    "Rato",
    "Umbigo",
  ].map((letter) => letter.toUpperCase());

  // classes
  class Forca {
    constructor(
      word,
      selectedLetters,
      player1,
      player2,
      round,
    ) {
      this.word = word;
      this.selectedLetters = selectedLetters;
      this.player1 = player1;
      this.player2 = player2;
      this.turn = player1.id;
      this.round = round;
    }
  }

  class Player {
    constructor(name, id, color = '#fb1', points = 0, dollParts = 0) {
      this.name = name;
      this.id = id;
      this.color = color;
      this.points = points;
      this.dollParts = dollParts;
    }
  }

  //Objects

  let click = false;

  let modal = {
    type: false,
    player: '',
    color: '',
  }

  const name1 = window.prompt("Digite o nome do Jogador 1 :");
  const name2 = window.prompt("Digite o nome do Jogador 2 :");

  let player1 = new Player(name1, 1, "#F04444");
  let player2 = new Player(name2, 2, "#4489F0");
  let forca = new Forca(randomWord(words), [], player1, player2, 1);

  //Functions
  function resetGame() {
    player1 = new Player(name1, 1, "#F04444");
    player2 = new Player(name2, 2, "#4489F0");
    forca = new Forca(randomWord(words), [], player1, player2, 1);
    modal = {
      type: false,
      player: '',
      color: '',
    }
  }

  function randomWord(words) {
    const number = Math.floor(Math.random() * words.length);
    return words[number];
  }

  function verifyAddPoint(word, selected) {
    const wordArr = word.split('');
    const boolean = wordArr.every((e) => selected.filter((selec) => selec === e).length > 0);
    return boolean;
  }

  function formatStr(str){
    const formated = str.normalize("NFD").replace(/[\u0300-\u036f]/g, "");
    return formated;
  }

  function formatArrStr(arr){
    const formated = arr.map((str) => str.normalize("NFD").replace(/[\u0300-\u036f]/g, ""));
    return formated;
  }

  function clickKeyBoard(letter) {
    let {selectedLetters, word, turn, player1, player2} = forca;
    
    if(!selectedLetters.includes(formatStr(letter))) {
      const selected = selectedLetters.concat(letter);
      forca.selectedLetters = selected;
    }

    if(forca.round > 3) {
      if(player1.points > player2.points) {
        modal = {
            type: 'victory',
            player: player1.name,
            color: player1.color,
        }
        return ;
      }else if(player1.points < player2.points) {
        modal = {
            type: 'victory',
            player: player2.name,
            color: player2.color,
        }
        return ;
      } else {
        modal = {type: 'active'};
        return ;
      }
    }

    if(player1.dollParts >= 5 && player2.dollParts >= 5) {
      player1 = {...player1, dollParts: 0};
      player2 = {...player2, dollParts: 0};
      forca = new Forca(randomWord(words), [], player1, player2, forca.round + 1);
      return ;
    }

    if(verifyAddPoint(word, forca.selectedLetters)) {
      if(forca.turn === player1.id){
        player1 = {...player1, dollParts: 0, points: player1.points + 1};
        player2 = {...player2, dollParts: 0};
        forca = new Forca(randomWord(words), [], player1, player2, forca.round + 1);
        return ;
      } else {
        player1 = {...player1, dollParts: 0};
        player2 = {...player2, dollParts: 0, points: player2.points + 1};
        forca = new Forca(randomWord(words), [], player1, player2, forca.round + 1);
        return ;
      }
    }
    
    if(!formatArrStr(word.split('')).includes(letter)){
      if(turn === player1.id  && !click) {
        click = true;
        const dollParts = player1.dollParts + 1;
        forca.player1 = {...player1, dollParts};
        
        if(player2.dollParts < 6){
          setTimeout(() => {
            forca.turn = player2.id;
            click = false;
          }, 1100);
        }
      } else if(!click) {
        click = true;
        const dollParts = player2.dollParts + 1;
        forca.player2 = {...player2, dollParts};
                
        if(player1.dollParts < 6){
          click = true;
          setTimeout(() => {
            forca.turn = player1.id;
            click = false;
          }, 1100);
        }
      }
    }
  }
</script>

<svelte:head>
  <title>Forca | Jogando</title>
</svelte:head>
<main class="wrapper">
  <div class="info-container shadow-container">
    <SelectedLetters title="Letras escolhidas" letters={forca.selectedLetters} />
    <BackButton href="/" style="position: absolute; top: 2rem; right: .7rem;" />
    <PlayersCard players={[forca.player1, forca.player2]} turn={forca.turn} round={forca.round <=3 ? forca.round : 3} />
    <div id="forca-layout">
      <div id="forca">
        <StickmanSvg player={forca.turn === forca.player1.id ? forca.player1 : forca.player2} />
        <ForcaSvg />
      </div>
      <Letters letters= {forca.word.split('')} selected={forca.selectedLetters} />
      <KeyBoardGame onClick={clickKeyBoard} />
    </div>
  </div>
  {#if modal.type === 'victory'}
    <Modal onClick={resetGame}>
      <h2 slot="title">Vitória do jogador <span style={`color: ${modal.color}`}>{modal.player}</span>!</h2>
    </Modal>
  {:else if modal.type === 'active'}
    <Modal onClick={resetGame}>
      <h2 slot="title">Não houveram vencedores!</h2>
    </Modal>
  {/if}
</main>

<style>
  .info-container {
    min-height: 34.7rem;
    position: relative;
  }

  #forca-layout {
    width: 80%;
    margin: auto;
    padding: 1.3rem 0;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
  }

  #forca {
    position: relative;
  }
</style>
