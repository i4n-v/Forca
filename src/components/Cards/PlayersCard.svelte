<script>
  export let players = [];
</script>

<div id="players-container">
  {#each players as player}
    <div>
      <span class="player">{player.name && player.name}</span>
      <div class="point" style={`background-color: ${player.color ? player.color : '#000'}`}>{player.points && player.points}</div>
    </div>
  {/each}
</div>

<style>
  #players-container {
    display: flex;
    flex-direction: column;
    gap: .5rem;
    position: absolute;
    top: 8rem;
    right: .7rem;
  }

  #players-container > div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: .5rem;
    gap: .5rem;
  }

  .player {
    font-size: 1.3rem;
    color: var(--colorFive);
    font-weight: bold;
  }

  .point {
    padding: .1rem .5rem;
    border-radius: .2rem;
    color: #fff;
  }
</style>