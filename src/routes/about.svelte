<main>
  <h1>A Bit About Me</h1>
  <p class="desc">
    Currently, I'm a QA Tester working on the enhancing user experince at Babel
    Media. Previously, I did frontend web development to build delightful UI &
    UX for emerging companies. I was a freelance web and brand designer, and
    worked with Polardot.in to help multiple companies to build their digital
    footprint. I was also an intern at Tech4i. <br /><br /> Want to work
    together?
    <a href="/contact">Contact me</a>.
  </p>
  <h2>History</h2>
  <ul>
    <li>
      <p>QA Tester - Babel Media Pvt. Ltd. (A Keywords Studios)</p>
      <p>Sep 2019 - Currently Working Here</p>
    </li>
    <li>
      <p>Intern - Tech4i Pvt. Ltd.</p>
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
      <p>Intermediate - Dr. D. RAM D.A.V. Public School</p>
      <p>2015</p>
    </li>
    <li>
      <p>Matriculation - Dr. D. RAM D.A.V. Public School</p>
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
