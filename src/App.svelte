<script>
  import Record from './lib/Record.svelte';

  let windowWidth = window.innerWidth;
  let width;
  let height;

  if (windowWidth > 800) {
    width = 400;
    height = 400;
  } else {
    width = 250;
    height = 250;
  }
</script>

<main>
  <h1 class="name">andreas lindberg</h1>
  {#if width > 250}
    <div class="record-desktop">
      <Record {height} {width} />
    </div>
  {:else}
    <div class="record">
      <Record {height} {width} />
    </div>
  {/if}
  <h1 class="title">web developer based in gothenburg</h1>
</main>

<style>
  main {
    height: 100vh;
    width: 100vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    pointer-events: none;
  }

  .record {
    height: 250px;
    width: 280px;
    display: flex;
    align-items: center;
    justify-content: center;
    animation: spin 1.8s linear infinite;
  }

  .record-desktop {
    height: 400px;
    width: 400px;
    display: flex;
    justify-content: center;
    align-items: center;
    animation: spin 1.8s linear infinite;
  }

  h1 {
    font-family: 'Courier New', Courier, monospace;
    color: #fcfbe3;
    letter-spacing: 2px;
    font-weight: 400;
    padding: 32px 0;
    text-align: center;
    line-height: 110%;
  }

  @keyframes spin {
    100% {
      transform: rotate(360deg);
    }
  }
</style>
