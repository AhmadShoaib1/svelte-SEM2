<script>
  import { onMount } from "svelte";
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher(); // Creating event dispatcher instance
  // Variable to store the fetched data 
  let quote = "";
  let anime = "";
  let character = "";
  let search = "";
  let picURL = ""; 
  const base_url = `https://api.unsplash.com`;
  const client_id = `2A2-AhB7VAcSfcQG00esnMfFkaJSeUOWEqrXwq0Tdcs`;

  const delay = (ms) => new Promise(resolve => setTimeout(resolve, ms));  // adding delay because the send api should run after the first

  const handleSearch = async () => {
    let counter = 0;
    const maxAttempts = 5;
    // Retry fetching data up to maxAttempts times in case of failure because the first api is not a good one and it fails sometimes but some give you data
    //so i set this as a counter measure in case if the api didnt return any data
    while (counter < maxAttempts) {
      try {
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

        await delay(1000); // Introducing a delay before fetching image
        picsearch();

        break; 
      } catch (e) {
        console.error("Error fetching data:", e);
        counter++;
      }
    }
  };
  // Function to search for an image related to the anime
  const picsearch = async () => {
    const response = await fetch(`${base_url}/search/photos?query=${search}&per_page=1&client_id=${client_id}`);
    const data = await response.json();
    picURL = data.results[0].urls.regular; 
    console.log(picURL);
  }

  onMount(() => {
    handleSearch();
  });
</script>
<!--the fetched data being shown-->
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
<!-- Displaying the fetched image if there is nay available -->
<div class="q-pic">
  {#if picURL}
    <img src={picURL} alt="Fetched Anime" />
  {/if}
</div>
