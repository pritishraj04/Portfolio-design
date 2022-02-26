<script>
  import Header from "$lib/Header.svelte";
  import "../app.scss";
</script>

<Header />
<slot />
<p class="footer-text">Designed and Developed by Pritish Raj</p>

<style lang="scss">
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
