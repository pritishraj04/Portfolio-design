<script>
  // import PC from "$lib/PC.svelte";

  import Key from "$lib/Key.svelte";

  let y;
</script>

<svelte:head>
  <title>Pritish | Home</title>
</svelte:head>

<svelte:window bind:innerHeight={y} />

<main style="margin-top: max({y / 2 - 214}px, 140px);" id="main">
  <h2>
    Hello. I am <span class="accent">Pritish Raj</span>.<br />
    <span class="accent">Software Engineer</span> from
    <span class="accent">New Delhi</span>.
  </h2>
  <p>
    Right now I'm looking for new opportunites. <br /> Currently working at
    <span class="italic">Babel Media Pvt. Ltd.</span>
    as <span class="italic">QA Tester</span>.
  </p>
</main>
<div class="pc" style="top: max({y / 2 - 214}px, 170px);">
  <Key char="w" />
  <Key char="a" />
  <Key char="s" />
  <Key char="d" />
</div>

<p class="footer-text">Designed and Developed by Pritish Raj</p>

<style lang="scss">
  main {
    /* min-height: calc(100vh - 5rem); */
    /* margin-block: max(10rem, 18%) 0; */
    /* transform: translateY(-50%); */
    h2 {
      font-weight: 700;
      font-size: clamp(1.5rem, 2.4vw, 4.125rem);
    }
    p {
      font-size: clamp(0.5rem, 1.2vw, 2.125rem);
    }
  }
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
