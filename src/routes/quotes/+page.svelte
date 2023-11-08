<script>
  import { onMount } from "svelte";
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  let quote = "";
  let anime = "";
  let character = "";
  let search = "";

  const handleSearch = async () => {
    let counter = 0;
    const maxAttempts = 5;

    while (counter < maxAttempts) {
      try {
       
        console.log("Fetch URL:", `https://animechan.xyz/api/random/anime?title=${search}`);

        const response = await fetch(`https://animechan.xyz/api/random/anime?title=${search}`);

        const {
          anime: tempAnime,
          character: tempCharacter,
          quote: tempQuote,
        } = await response.json();
        console.log(tempAnime, tempCharacter, tempQuote);

        anime = tempAnime;
        character = tempCharacter;
        quote = tempQuote;

        break; 
      } catch (e) {
        console.error("Error fetching data:", e);
        counter++;
      }
    }
  };

  onMount(handleSearch);
</script>

<div class="quotes">
  <div class="quote-container">
    <div class="search-container">
      <input bind:value={search} placeholder="Enter Anime Title" />
      <button class="searchbutton" on:click={handleSearch}>Search</button>
    </div>
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
