<script>
  import image from '/record.png';

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
    </div>
  {:else}
    <div class="record">
      <img class="record-image" alt="record" src={image} />
    </div>
  {/if}
  <h1 class="title">web developer based in gothenburg</h1>
</main>

<style>
  main {
    background-color: #fff;
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
    box-shadow: 0px 0px 30px #0007;
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
    box-shadow: 0px 0px 30px #0007;
    align-items: center;
    animation: spin 1.8s linear infinite;
  }

  h1 {
    font-family: 'Courier New', Courier, monospace;
    color: #234b9a;
    letter-spacing: 2px;
    font-weight: 200;
    padding: 32px 0;
    text-align: center;
    line-height: 110%;
  }

  h1::selection {
    background: #fcbd00;
  }

  img::selection {
    background: none;
  }

  @keyframes spin {
    100% {
      transform: rotate(360deg);
    }
  }

  @media (prefers-color-scheme: dark) {
    main {
      background-color: #242424;
    }
    .record {
      box-shadow: none;
    }
    .record-desktop {
      box-shadow: none;
    }
    h1 {
      color: #fcfbe3;
    }

    h1::selection {
      background: #234b9a;
    }
  }
</style>
