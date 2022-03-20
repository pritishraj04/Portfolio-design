<script>
  import Header from "$lib/Header.svelte";
  import { page } from "$app/stores";
  import "../app.scss";
</script>

<Header />
<slot />
{#if $page.url.pathname !== "/"}
  <p class="footer-text">Designed and Developed by Pritish Raj</p>
{/if}

<style lang="scss">
  .footer-text {
    position: fixed;
    font-size: clamp(0.5rem, 1vw, 1.25rem);
    color: hsla(0, 0%, 89%, 0.3);
    bottom: 10rem;
    right: 1rem;
    transform: translateX(50%) rotate(-90deg);
    @media only screen and (max-width: 540px) {
      bottom: 25%;
      right: -4rem;
      transform: none;
      transform: rotate(-90deg);
    }
  }
</style>
