<script>
  import Record from './lib/Record.svelte';
  import image from '/asdf.png';

  let windowWidth = window.innerWidth;
  let width;

  if (windowWidth > 800) {
    width = 400;
  } else {
    width = 250;
  }
</script>

<main>
  <h1 class="name">andreas lindberg</h1>
  {#if width > 250}
    <div class="record-desktop">
      <img class="record-image-desktop" alt="record" src={image} />
      <!-- <Record {height} {width} /> -->
    </div>
  {:else}
    <div class="record">
      <img class="record-image" alt="record" src={image} />
      <!-- <Record {height} {width} /> -->
    </div>
  {/if}
  <h1 class="title">web developer based in gothenburg</h1>
</main>

<style>
  main {
    background-color: #242424;
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
    width: 250px;
    display: flex;
    border-radius: 50%;
    align-items: center;
    justify-content: center;
    /* box-shadow: 0px 0px 30px #0007; */
    animation: spin 1.8s linear infinite;
  }

  .record-image {
    width: 250px;
    height: 250px;
  }

  .record-image-desktop {
    width: 400px;
    height: 400px;
  }
  .record-desktop {
    height: 400px;
    width: 400px;
    display: flex;
    border-radius: 50%;
    justify-content: center;
    /* box-shadow: 0px 0px 30px #0007; */
    align-items: center;
    animation: spin 1.8s linear infinite;
  }

  h1 {
    font-family: 'Courier New', Courier, monospace;
    /* color: #fcbd00;
    color: #234b9a; */
    color: #fcfbe3;

    letter-spacing: 2px;
    font-weight: 800;
    padding: 32px 0;
    text-align: center;
    line-height: 110%;
  }

  @keyframes spin {
    100% {
      transform: rotate(360deg);
      /* transform-origin: center center; */
    }
  }
</style>
