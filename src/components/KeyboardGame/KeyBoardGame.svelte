<script>
  import { GameButton } from '../';

  export let onClick = () => {};
</script>

<div class="keyboard">
  <GameButton letter="A" onClick={onClick}/>
  <GameButton letter="B" onClick={onClick}/>
  <GameButton letter="C" onClick={onClick}/>
  <GameButton letter="D" onClick={onClick}/>
  <GameButton letter="E" onClick={onClick}/>
  <GameButton letter="F" onClick={onClick}/>
  <GameButton letter="G" onClick={onClick}/>
  <GameButton letter="H" onClick={onClick}/>
  <GameButton letter="I" onClick={onClick}/>
  <GameButton letter="J" onClick={onClick}/>
  <GameButton letter="K" onClick={onClick}/>
  <GameButton letter="L" onClick={onClick}/>
  <GameButton letter="M" onClick={onClick}/>
  <GameButton letter="N" onClick={onClick}/>
  <GameButton letter="O" onClick={onClick}/>
  <GameButton letter="P" onClick={onClick}/>
  <GameButton letter="Q" onClick={onClick}/>
  <GameButton letter="R" onClick={onClick}/>
  <GameButton letter="S" onClick={onClick}/>
  <GameButton letter="T" onClick={onClick}/>
  <GameButton letter="U" onClick={onClick}/>
  <GameButton letter="V" onClick={onClick}/>
  <GameButton letter="W" onClick={onClick}/>
  <GameButton letter="X" onClick={onClick}/>
  <GameButton letter="Y" onClick={onClick}/>
  <GameButton letter="Z" onClick={onClick}/>
</div>

<style>
  .keyboard {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: .8rem;
  }
</style>