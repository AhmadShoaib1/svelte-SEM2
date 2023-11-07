<script>
  import { onMount } from "svelte";
  let quote = "";

  onMount(async () => {

    // This is bad. Figure out why the CORS errors are happening.
    // let notFetched = true;
    // while (notFetched) {
    //   try {
    //     const response = await fetch(
    //       "https://animechan.xyz/api/random/anime?title=naruto"
    //     );

    //     const tempQuote = await response.json();
    //     console.log(tempQuote);

    //     quote = tempQuote.quote;
    //     notFetched = false;
    //   } catch (e) {}
    // }

    const res = await fetch(`https://narutodb.xyz/api/character?page=${Math.floor(Math.random() * 100)}&limit=1`);
    const character =  await res.json();
    console.log(character)
  });
</script>

<div class="quote">{quote}</div>
