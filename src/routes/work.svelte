<main>
  <h1>Things I've worked on</h1>
  <section class="works">
    <div class="work-card">
      <img
        src="https://via.placeholder.com/365x265?text=Work+Image"
        alt="work-img"
      />
      <h4>Title</h4>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>
    </div>
    <div class="work-card">
      <img
        src="https://via.placeholder.com/365x265?text=Work+Image"
        alt="work-img"
      />
      <h4>Title</h4>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>
    </div>
    <div class="work-card">
      <img
        src="https://via.placeholder.com/365x265?text=Work+Image"
        alt="work-img"
      />
      <h4>Title</h4>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>
    </div>
    <div class="work-card">
      <img
        src="https://via.placeholder.com/365x265?text=Work+Image"
        alt="work-img"
      />
      <h4>Title</h4>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>
    </div>
    <div class="work-card">
      <img
        src="https://via.placeholder.com/365x265?text=Work+Image"
        alt="work-img"
      />
      <h4>Title</h4>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>
    </div>
    <div class="work-card">
      <img
        src="https://via.placeholder.com/365x265?text=Work+Image"
        alt="work-img"
      />
      <h4>Title</h4>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>
    </div>
  </section>
</main>

<style lang="scss">
  main {
    margin-top: 2rem;
    h1 {
      font-weight: 400;
      font-size: clamp(1.6rem, 2.2vw, 3.125rem);
      margin-bottom: 2rem;
    }
    .works {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      column-gap: 2.5rem;
      row-gap: 1.5rem;
      @media only screen and (max-width: 768px) {
        grid-template-columns: repeat(2, 1fr);
      }
      @media only screen and (max-width: 425px) {
        grid-template-columns: 1fr;
      }
      .work-card {
        img {
          width: 100%;
        }
        h4 {
          font-weight: 400;
          font-size: clamp(1rem, 1.6vw, 2.725rem);
          margin-bottom: 0.2rem;
        }
        p {
          font-size: clamp(0.8rem, 0.9vw, 1.925rem);
          line-height: 0.98;
        }
      }
    }
  }
</style>
