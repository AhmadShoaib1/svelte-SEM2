<script>
    let onePieceCharacters = [
      {
        name: "Monkey D. Luffy",
        image: "luffy.jpg",
      },
      {
        name: "Roronoa Zoro",
        image: "zoro.jpg",
      },
      {
        name: "Red Hair Shanks",
        image: "shanks.jpg",
      },
      {
        name: "Dracule Mihawk",
        image: "mihawk.jpg",
      },
    ];
    let onePieceAdditionalInfo = "Discover the adventures of the Straw Hat Pirates in 'One Piece,' a journey filled with friendship, dreams, and epic battles!";
  </script>
  
  <svelte:head>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" />
  </svelte:head>
  <body>
    <div class="op-additional-info">  <!-- Container for additional information about "One Piece" -->
      <p>{onePieceAdditionalInfo}</p>
    </div>
    <div class = "button-container">    <!-- Container for the "Start Watching" button -->
      <a href="https://aniwave.to/watch/one-piece.ov8/ep-1" target="_blank" class="watch-button">
        <button class="op-button">Start Watching</button>
      </a>
    </div>
  
    <div class="op-anime-container">
      {#each onePieceCharacters as { name, image } (name)}      <!-- Iterate over each character entry in the onePieceCharacters list -->
        <div class="op-anime-entry grid">
          <div class="op-name-container s1">    <!-- Container for the character's name -->
            <h2>{name}</h2>
          </div>
          <div class="op-image-container s2">   <!-- Container for the character's image -->
            <img src={`../img/${image}`} alt={name} />
          </div>
        </div>
      {/each}
    </div>
  </body>
  