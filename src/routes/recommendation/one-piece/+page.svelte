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
    <link rel="stylesheet" href="static/css/main.css" />
  </svelte:head>
  <body>
    <div class="op-additional-info">
      <p>{onePieceAdditionalInfo}</p>
    </div>
  
    <div class="op-anime-container">
      {#each onePieceCharacters as { name, image } (name)}
        <div class="op-anime-entry grid">
          <div class="op-name-container s1">
            <h2>{name}</h2>
          </div>
          <div class="op-image-container s2">
            <img src={`../img/${image}`} alt={name} />
          </div>
        </div>
      {/each}
    </div>
  </body>
  