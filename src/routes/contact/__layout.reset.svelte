<script>
  import Header from "$lib/Header.svelte";
  import Icon from "@iconify/svelte";
  import mailIcon from "@iconify/icons-bytesize/mail.js";
  import phoneIcon from "@iconify/icons-bi/phone.js";
  import githubOutlineFill from "@iconify/icons-akar-icons/github-outline-fill.js";
  import linkedinOutlined from "@iconify/icons-ant-design/linkedin-outlined.js";
</script>

<svelte:head>
  <title>Pritish | Contact</title>
</svelte:head>

<Header />
<main>
  <h1>Get in touch with me</h1>
  <p class="info">Average response time: 48 Hrs.</p>
  <section class="contact">
    <div class="contact-data">
      <div class="single-contact">
        <Icon width={30} icon={mailIcon} />
        <a href="mailto:pritishraj04@gmail.com">pritishraj04@gmail.com</a>
      </div>
      <div class="single-contact">
        <Icon width={30} icon={phoneIcon} />
        <a href="tel:+919097785207">+91-9097785207</a>
      </div>
      <div class="single-contact">
        <Icon width={30} icon={githubOutlineFill} />
        <a
          href="https://www.github.com/pritishraj04"
          target="_blank"
          rel="noopener noreferrer">github.com/pritishraj04</a
        >
      </div>
      <div class="single-contact">
        <Icon width={30} icon={linkedinOutlined} />
        <a
          href="https://www.linkedin.com/in/pritishraj04"
          target="_blank"
          rel="noopener noreferrer">linkedin.com/in/pritishraj04</a
        >
      </div>
    </div>
    <slot />
  </section>
</main>
<p class="footer-text">Designed and Developed by Pritish Raj</p>

<style lang="scss">
  main {
    margin-top: 2rem;
    h1 {
      font-weight: 400;
      font-size: clamp(1.6rem, 2.2vw, 3.125rem);
    }
    .info {
      margin-bottom: 2rem;
      font-size: clamp(0.6rem, 1vw, 1.5rem);
    }
    a {
      font-size: clamp(0.8rem, 1.2vw, 1.925rem);
    }
    .contact {
      display: grid;
      grid-template-columns: 2.8fr 1fr;
      column-gap: 2rem;
      grid-row: auto;
      @media only screen and (max-width: 768px) {
        grid-template-columns: 1fr;
      }
      .contact-data {
        order: 1;
        margin-bottom: 2rem;
        @media only screen and (max-width: 768px) {
          order: 0;
        }
        .single-contact {
          display: flex;
          align-items: center;
          margin-top: 0.5rem;
          gap: 1rem;
          &:first-child {
            margin-top: 0;
          }
        }
      }
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
