<script>
  import { onMount } from "svelte";

  export let text;
  export let waitTime = 0;
  let typingtxt = ``;

  let i = 0;
  const speed = 100;

  const typeWriter = () => {
    if (i < text.length) {
      typingtxt += text.charAt(i);
      i++;
      setTimeout(typeWriter, speed);
    }
  };
  onMount(() => {
    setTimeout(typeWriter, waitTime * 1000);
  });
</script>

{typingtxt}
