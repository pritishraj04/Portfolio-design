<script>
  import { page } from "$app/stores";
  let x;
</script>

<svelte:window bind:innerWidth={x} />

<header>
  <div class="logo">
    <a href="/">PR</a>
  </div>
  <a class="skip-to-content-link" href="#main"> Skip to content </a>
  <nav>
    <ul>
      <li>
        <a
          sveltekit:prefetch
          href="/about"
          class:active={$page.url.pathname == "/about"}>About</a
        >
      </li>
      <li>
        <a
          sveltekit:prefetch
          href="/work"
          class:active={$page.url.pathname == "/work"}>Work</a
        >
      </li>
      {#if $page.url.pathname == "/contact" && x <= 540}
        <div />
      {:else}
        <li>
          <a sveltekit:prefetch href="/contact" class="cta">Get in Touch</a>
        </li>
      {/if}
    </ul>
  </nav>
</header>

<style lang="scss">
  .skip-to-content-link {
    background: var(--clr-secondary-bg);
    height: 30px;
    left: 50%;
    padding: 8px;
    position: absolute;
    transform: translateY(-120%);
    transition: transform 0.3s;
  }

  .skip-to-content-link:focus {
    transform: translateY(0%);
  }
  header {
    display: flex;
    justify-content: space-between;
    margin: 0 auto;
    max-width: 75%;
    @media only screen and (max-width: 425px) {
      max-width: 93%;
    }
    @media only screen and (max-width: 1440px) {
      max-width: 85%;
    }
    ul {
      display: flex;
      align-items: center;
      min-height: 4.2rem;
      gap: 3rem;
      @media only screen and (max-width: 540px) {
        gap: 0;
      }
      li {
        @media only screen and (max-width: 540px) {
          &:first-child {
            margin-right: 1.4rem;
          }
        }
        a {
          font-size: clamp(0.9rem, 1.6vw, 2.5rem);
          font-weight: 500;
          &.active {
            font-weight: 600;
            text-decoration: underline;
          }
        }
      }
    }
  }
  .logo {
    font-size: clamp(1.5rem, 2.9vw, 4.5rem);
    font-weight: 700;
    margin-block: auto;
  }
  .cta {
    background: var(--clr-secondary-bg);
    padding-inline: 0.563rem;
    padding-block: 3rem 0.188rem;
    &:hover {
      color: var(--clr-primary-bg);
      background: var(--clr-primary-comp);
    }
    @media only screen and (max-width: 540px) {
      position: fixed;
      bottom: 0.5rem;
      left: 50%;
      transform: translateX(-50%);
      padding-block: 0.8rem;
      width: 90%;
      text-align: center;
      z-index: 99;
      /* @supports (backdrop-filter: blur(10px)) {
        @include bg-blur-light;
        &:hover {
          color: var(--clr-primary-bg);
          background: var(--clr-primary-comp);
        }
      } */
      &::before {
        content: "";
        position: absolute;
        background: var(--clr-primary-bg);
        width: 100%;
        height: 10px;
        left: 0;
        top: 99%;
      }
    }
  }
</style>
