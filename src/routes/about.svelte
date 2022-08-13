<svelte:head>
  <title>Pritish | About</title>
</svelte:head>

<main id="main">
  <h1>A Bit About Me</h1>
  <p class="desc">
    Currently, I'm a Test engineer working on perfecting user interface and
    enhancing user experince at <a
      href="https://creatiosoft.com/"
      target="_blank"
      class="creatiosoft_link"
      rel="noopener noreferrer">Creatiosoft Pvt. Ltd.</a
    >. Prior to this role i was assigned a role of FQA Tester at
    <a
      href="https://www.babelmedia.com/"
      class="babel_link"
      target="_blank"
      rel="noopener noreferrer"
    >
      Babel Media Pvt. Ltd.</a
    >. In this role i have worked on multiple projects including AAA games. I
    also have worked in Agile work environment. I am well versed in different
    testing techniques and tools. <br />
    Previously, I have done web development to build enhanced UI & UX for emerging
    companies. I was a freelance web and brand designer and developer, and worked
    with
    <a
      href="http://www.polardot.in"
      class="polardot_link"
      target="_blank"
      rel="noopener noreferrer">Polardot.in</a
    >
    to help multiple companies to build their digital footprint. I was also an intern
    at Tech4i Pvt. Ltd.. <br /><br /> Want to work together?
    <a href="/contact">Contact me</a>.
  </p>
  <h2>History</h2>
  <ul>
    <li>
      <p>Test Engineer - Creatiosoft Pvt. Ltd., Noida</p>
      <p>May 2022 - Currently Working Here</p>
    </li>
    <li>
      <p>QA Tester - Babel Media Pvt. Ltd. (A Keywords Studios), Gurugram</p>
      <p>Sep 2019 - May 2022</p>
    </li>
    <li>
      <p>Intern - Tech4i Pvt. Ltd., New Delhi</p>
      <p>May 2018 - Jun 2018</p>
    </li>
  </ul>
  <h2>Education</h2>
  <ul>
    <li>
      <p>B. Tech - Amity University</p>
      <p>Mar 2015 - May 2019</p>
    </li>
    <li>
      <p>Intermediate - D.A.V. Public School</p>
      <p>2015</p>
    </li>
    <li>
      <p>Matriculation - D.A.V. Public School</p>
      <p>2012</p>
    </li>
  </ul>
</main>

<style lang="scss">
  main {
    margin-top: 2rem;
    h1 {
      font-weight: 400;
      font-size: clamp(1.6rem, 2.2vw, 3.125rem);
      margin-bottom: 0.5rem;
    }
    h2 {
      font-weight: 400;
      font-size: clamp(1.2rem, 1.9vw, 2.925rem);
      margin-bottom: 0.5rem;
    }
    p {
      font-size: clamp(0.8rem, 1.2vw, 1.925rem);
    }
    .desc {
      max-width: 60%;
      margin-bottom: 1.5rem;
      @media only screen and (max-width: 720px) {
        max-width: unset;
      }
      .polardot_link {
        color: var(--clr-primary-polardot);
      }
      .creatiosoft_link {
        color: var(--clr-primary-creatiosoft);
      }
      .babel_link {
        color: var(--clr-primary-babel);
      }
    }
    ul {
      margin-bottom: 2rem;
      border-left: white 1px solid;
      padding-left: 1.2rem;
      li {
        position: relative;
        &::before {
          content: "•";
          font-size: 4rem;
          position: absolute;
          left: -2.05rem;
          top: -1.4rem;
        }
        p {
          &:last-child {
            margin-bottom: 1.2rem;
          }
        }
      }
    }
  }
</style>
