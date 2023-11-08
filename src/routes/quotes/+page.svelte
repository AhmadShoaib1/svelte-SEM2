<script>
  import { onMount } from "svelte";
  let quote = "";
  let anime = "";
  let character = "";

  onMount(async () => {
    // This is bad. Figure out why the CORS errors are happening.
    let notFetched = true;
    while (notFetched) {
      try {
        const response = await fetch(
          "https://animechan.xyz/api/random/anime?title=naruto"
        );

        const {
          anime: tempAnime,
          character: tempCharacter,
          quote: tempQuote,
        } = await response.json();
        console.log(tempAnime, tempCharacter, tempQuote);

        anime = tempAnime;
        character = tempCharacter;
        quote = tempQuote;
        notFetched = false;
      } catch (e) {}
    }
  });
</script>

<div class = "quotes">
  <div class="quote-container">
    <div class="info-row">
      <p>Character: {character}</p>
    </div>
    <div class="info-row">
      <p>From: {anime}</p>
    </div>
    <div class="info-row">
      <p>{quote}</p>
    </div>
  </div>
</div>
