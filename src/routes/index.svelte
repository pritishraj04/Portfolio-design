<script>
  // import PC from "$lib/PC.svelte";
  import Hero from "$lib/Hero.svelte";
  import Key from "$lib/Key.svelte";

  let y;
</script>

<svelte:head>
  <title>Pritish | Home</title>
</svelte:head>

<svelte:window bind:innerHeight={y} />

<main style="margin-top: max({y / 2 - 214}px, 140px);" id="main">
  <Hero />
</main>
<div class="pc" style="top: max({y / 2 - 214}px, 170px);">
  <Key char="w" />
  <Key char="a" />
  <Key char="s" />
  <Key char="d" />
</div>

<p class="footer-text">Designed and Developed by Pritish Raj</p>

<style lang="scss">
  /* main {
    min-height: calc(100vh - 5rem);
    margin-block: max(10rem, 18%) 0;
    transform: translateY(-50%);
  } */
  .pc {
    position: absolute;
    right: 0;
    padding: 3rem;
    padding-right: 1rem;
    overflow: hidden;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 8px;
    @media only screen and (max-width: 770px) {
      filter: blur(5px);
      z-index: -1;
    }
  }
  .footer-text {
    position: fixed;
    font-size: clamp(0.5rem, 1vw, 1.25rem);
    color: hsla(0, 0%, 89%, 0.3);
    bottom: 0.5rem;
    right: 50%;
    transform: translateX(50%);
    @media only screen and (min-width: 541px) {
      &::before {
        content: "";
        position: absolute;
        background: var(--clr-primary-bg);
        width: 100%;
        height: 40px;
        top: 0;
        z-index: -1;
      }
    }
    @media only screen and (max-width: 540px) {
      bottom: 25%;
      right: -4rem;
      transform: none;
      transform: rotate(-90deg);
    }
  }
</style>
