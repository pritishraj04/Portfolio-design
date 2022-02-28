<script>
  import works from "$lib/works";
  let filter = { techFilter: [], categoryFilter: [] };
  let filteredList = works;

  const refreshList = (type) => {
    if (filter.techFilter.length === 0 && filter.categoryFilter.length === 0) {
      filteredList = works;
    } else {
      if (type === "category") {
        for (let i = 0; i < filter.categoryFilter.length; i++) {
          filteredList = works.filter((e) =>
            e.category.includes(filter.categoryFilter[i])
          );
        }
        filteredList = filteredList;
      } else {
        for (let i = 0; i < filter.techFilter.length; i++) {
          filteredList = works.filter((e) =>
            e.tech.includes(filter.techFilter[i])
          );
        }
        filteredList = filteredList;
      }
    }
  };

  const addFilter = (type, fil) => {
    switch (type) {
      case "category":
        if (!filter.categoryFilter.includes(fil)) {
          filter.categoryFilter = [...filter.categoryFilter, fil];
          refreshList("category");
        }
        break;
      case "tech":
        if (!filter.techFilter.includes(fil)) {
          filter.techFilter = [...filter.techFilter, fil];
          refreshList("tech");
        }
        break;
    }
  };
  const removeFilter = (type, fil) => {
    switch (type) {
      case "category":
        for (let i = 0; i < filter.categoryFilter.length; i++) {
          if (filter.categoryFilter[i] === fil) {
            filter.categoryFilter.splice(i, 1);
            refreshList("category");
          }
        }
        break;
      case "tech":
        for (let i = 0; i < filter.techFilter.length; i++) {
          if (filter.techFilter[i] === fil) {
            filter.techFilter.splice(i, 1);
            refreshList("tech");
          }
        }
        break;
    }
    filter = filter;
  };
</script>

<svelte:head>
  <title>Pritish | Work</title>
</svelte:head>

<main id="main">
  <h1>Things I've worked on</h1>
  <h3>
    Filter by: {#if filter.techFilter.length === 0 && filter.categoryFilter.length === 0}
      All
    {:else}
      {#each filter.techFilter as item}
        <button class="tech" on:click={() => removeFilter("tech", item)}
          >{item}</button
        >
      {/each}
      {#each filter.categoryFilter as item}
        <button class="category" on:click={() => removeFilter("category", item)}
          >{item}</button
        >
      {/each}
    {/if}
  </h3>
  <section class="works">
    {#each filteredList as work}
      <div class="work-card">
        <div class="techs">
          {#each work.tech as tech}
            <button
              class="tech"
              on:click={() => addFilter("tech", tech)}
              title={`Filter by ${tech}`}>{tech}</button
            >
          {/each}
        </div>
        <a href={work.link} target="_blank" rel="noopener noreferrer">
          <img src={`/asset/works/${work.img}`} alt={work.title} /></a
        >
        <div class="desc">
          <a href={work.link} target="_blank" rel="noopener noreferrer">
            <h4>{work.title}</h4></a
          >
          <button
            on:click={() => addFilter("category", work.category)}
            class="category"
            title={`Filter by ${work.category}`}>{work.category}</button
          >
          <a href={work.link} target="_blank" rel="noopener noreferrer">
            <p>
              {work.desc}
            </p></a
          >
        </div>
      </div>
    {:else}
      <h2>
        No items found. Try removing filters or please visit <a href="/">Home</a
        >
      </h2>
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
    h3 {
      font-size: clamp(1rem, 1.6vw, 2.725rem);
      font-weight: 600;
      margin-bottom: 1rem;
      button.tech {
        margin: 0.2rem;
        padding: 0.2rem;
        border-radius: 0.5rem;
        font-weight: 600;
      }
      button.category {
        margin: 0.2rem;
        padding: 0.2rem;
        border-radius: 0.5rem;
        font-weight: 600;
        background: var(--clr-primary-bg);
        border: 2px var(--clr-primary-text) solid;
        text-transform: capitalize;
      }
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
        border: 1px var(--clr-secondary-bg) solid;
        @media only screen and (min-width: 769px) {
          &:hover {
            background: var(--clr-primary-bg);
            transform: scale(1.1);
          }
        }
        img {
          width: 100%;
        }
        .desc {
          padding: 0.5rem;
          h4 {
            font-weight: 400;
            font-size: clamp(1rem, 1.6vw, 2.725rem);
            margin-bottom: 0.2rem;
          }
          .category {
            margin-block: 0.4rem;
            display: block;
            background: var(--clr-primary-bg);
            display: inline-block;
            text-transform: capitalize;
            font-size: clamp(0.7rem, 0.7vw, 1rem);
            font-weight: 600;
            border: 2px var(--clr-primary-text) solid;
            border-radius: 0.5rem;
            padding: 0.2rem;
          }
          p {
            font-size: clamp(0.8rem, 0.9vw, 1.925rem);
            line-height: 1.2;
            opacity: 0.7;
          }
        }
        .techs {
          position: absolute;
          max-height: 60%;
          @media only screen and (max-width: 768px) {
            position: unset;
            display: flex;
          }
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
            display: block;
            margin: 0.2rem;
            padding: 0.2rem;
            border-radius: 0.5rem;
            font-size: clamp(0.6rem, 0.6vw, 0.9rem);
            transform: scale(0);
            display: none;
            font-weight: 600;
            @media only screen and (max-width: 768px) {
              transform: scale(1);
              display: block;
            }
          }
        }
      }
    }
  }
</style>
