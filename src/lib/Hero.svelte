<script>
  import Typer from "$lib/Typer.svelte";
  import { isShown, pVisible } from "$lib/stores";
  import { fly } from "svelte/transition";
  let br = false;

  setTimeout(() => (br = true), 2400);
  setTimeout(() => {
    $pVisible = true;
  }, 7000);
  setTimeout(() => {
    $isShown = true;
  }, 8000);
</script>

{#if $isShown}
  <h2>
    Hello. I am
    <span class="accent">Pritish Raj.</span>
    <br />
    <span class="accent">Software Engineer</span>
    from
    <span class="accent">New Delhi.</span>
    <span class="blink" />
  </h2>
{:else}
  <h2>
    <Typer text="Hello. I am" />
    <span class="accent"><Typer text="Pritish Raj." waitTime="1.2" /></span>
    {#if br}
      <br />
    {/if}
    <span class="accent"><Typer text="Software Engineer" waitTime="2.5" /></span
    >
    <Typer text="from" waitTime="4.6" />
    <span class="accent"><Typer text="New Delhi." waitTime="5.4" /></span>
    <span class="blink" />
  </h2>
{/if}
{#if $pVisible}
  <p in:fly={{ y: 50, duration: 1000 }}>
    Right now I'm looking for new opportunites in Test Automation and Web
    development. <br /> Currently working at
    <span class="italic">Creatiosoft Pvt. Ltd.</span>
    as a <span class="italic">Test Engineer</span>.
  </p>
{/if}

<style>
  h2 {
    font-weight: 700;
    font-size: clamp(1.5rem, 2.4vw, 4.125rem);
  }
  p {
    font-size: clamp(0.5rem, 1.2vw, 2.125rem);
  }

  .blink {
    animation: blink 0.5s step-end infinite alternate;
    border-right: 3px solid;
    padding-right: 5px;
  }
  @keyframes blink {
    50% {
      border-color: transparent;
    }
  }
</style>
