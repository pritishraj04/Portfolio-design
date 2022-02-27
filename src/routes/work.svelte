<script>
  import works from "$lib/works";
</script>

<main>
  <h1>Things I've worked on</h1>
  <section class="works">
    {#each works as work}
      <a
        href={work.link}
        target="_blank"
        rel="noopener noreferrer"
        class="work-card"
      >
        <div class="techs">
          {#each work.tech as tech}
            <a href="/" class="tech" title={`Filter by ${tech}`}
              ><h5>{tech}</h5></a
            >
          {/each}
        </div>
        <img src={`/asset/works/${work.img}`} alt={work.title} />
        <h4>{work.title}</h4>
        <a href="/" class="category" title={`Filter by ${work.category}`}
          ><h5>{work.category}</h5></a
        >
        <p>
          {work.desc}
        </p>
      </a>
    {:else}
      <h2>Someting went wrong. Please visit <a href="/">Home</a></h2>
    {/each}
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
        min-width: 6.25rem;
        transition: transform 0.3s ease;
        &:hover {
          background: var(--clr-primary-bg);
          transform: scale(1.1);
        }
        img {
          width: 100%;
        }
        h4 {
          font-weight: 400;
          font-size: clamp(1rem, 1.6vw, 2.725rem);
          margin-bottom: 0.2rem;
        }
        .category,
        .tech {
          margin-block: 0.4rem;
          display: block;
          h5 {
            display: inline-block;
            text-transform: capitalize;
            font-size: clamp(0.7rem, 0.7vw, 1rem);
            border: 2px var(--clr-primary-text) solid;
            border-radius: 0.5rem;
            padding: 0.2rem;
          }
        }
        .techs {
          position: absolute;
          max-height: 60%;
          &::before {
            content: "⚙️";
            background: rgba(221, 221, 221, 0.7);
            @media only screen and (max-width: 768px) {
              content: "";
              background: none;
            }
          }
          &:hover .tech {
            transform: scale(1);
            display: block;
          }
          .tech {
            transition: transform 0.3s ease;
            margin-block: 0.2rem;
            transform: scale(0);
            display: none;
            @media only screen and (max-width: 768px) {
              transform: scale(1);
              display: block;
            }
            h5 {
              font-size: clamp(0.6rem, 0.6vw, 0.9rem);
              background: var(--clr-primary-bg);
            }
          }
        }
        p {
          font-size: clamp(0.8rem, 0.9vw, 1.925rem);
          line-height: 1.2;
          opacity: 0.7;
        }
      }
    }
  }
</style>
