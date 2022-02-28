<script>
  import PC from "$lib/PC.svelte";
  let y;
</script>

<svelte:head>
  <title>Pritish | Home</title>
</svelte:head>

<svelte:window bind:innerHeight={y} />

<main style="margin-top: max({y / 2 - 214}px, 140px);">
  <h2>
    Hello. I am <span class="accent">Pritish Raj</span>.<br />
    <span class="accent">Software Engineer</span> form
    <span class="accent">New Delhi</span>.
  </h2>
  <p>
    Right now I'm looking for new opportunites. <br /> Currently working at
    <span class="italic">Babel Media Pvt. Ltd.</span>
    as <span class="italic">QA Tester</span>.
  </p>
</main>
<div class="pc" style="top: max({y / 2 - 214}px, 170px);">
  <PC />
</div>

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
    right: 0rem;
    width: clamp(8rem, 23vw, 27rem);
    overflow: hidden;
    @media only screen and (max-width: 540px) {
      filter: blur(5px);
    }
  }
</style>
