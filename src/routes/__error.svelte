<script context="module">
  /** @type {import('@sveltejs/kit').ErrorLoad} */
  export function load({ error, status }) {
    return {
      props: {
        status,
        error,
      },
    };
  }
</script>

<script>
  export let status;
  export let error;
  console.log(error);
</script>

<main>
  <h1>{status}</h1>
  <h4>{`${error.name} : ${error.message}`}</h4>
  <p>{error.stack}</p>
</main>

<style lang="scss">
  main {
    text-align: center;
    h1 {
      color: rgb(192, 63, 63);
      font-weight: 800;
      font-size: clamp(2rem, 6vw, 10.25rem);
      margin-top: 2rem;
    }
    h4 {
      font-weight: 700;
      font-size: clamp(0.8rem, 1.4vw, 3.25rem);
      margin-top: 0.5rem;
    }
    p {
      font-size: clamp(0.5rem, 1vw, 1.925rem);
      opacity: 0.6;
      margin-top: 1rem;
      max-width: 50rem;
      max-height: 20rem;
      overflow-y: auto;
      overflow-x: visible;
      margin-inline: auto;
    }
  }
</style>
