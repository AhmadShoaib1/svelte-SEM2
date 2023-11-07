<script>
    let characters = [
      { name: "Monkey D. Luffy", image: "luffy.jpg" },
      { name: "Roronoa Zoro", image: "zoro.jpg" },
      { name: "Red-Haired Shanks", image: "shanks.jpg" },
      { name: "Dracule Mihawk", image: "mihawk.jpg" },
    ];
  
    function createTableRows() {
      const row = document.getElementById("characterRow");
  
      characters.forEach((character) => {
        const cell = document.createElement("td");
  
        const img = document.createElement("img");
        img.src = character.image;
        img.alt = character.name;
  
        const p = document.createElement("p");
        p.textContent = character.name;
  
        cell.appendChild(img);
        cell.appendChild(p);
        row.appendChild(cell);
      });
    }
  
    // Create table rows on component mount
    import { onMount } from "svelte";
    onMount(() => {
      createTableRows();
    });
  </script>
  
  <svelte:head>
    <link rel="stylesheet" href="css/main.css" />
  </svelte:head>
  
  <div class="header-op one-piece-section">
    <div class="description">
      <p>
        " One Piece, created by Eiichiro Oda, is an epic tale of adventure,
        friendship, and the pursuit of dreams. The story follows Monkey D.
        Luffy, a spirited young pirate with a dream to become the Pirate King by
        finding the legendary treasure known as One Piece. Luffy sets sail with
        his diverse crew, the Straw Hat Pirates, as they navigate the
        treacherous Grand Line, encounter formidable foes, and forge unbreakable
        bonds. The series is renowned for its rich world-building, complex
        characters, and themes of resilience and camaraderie. To embark on this
        thrilling journey, you can watch One Piece on streaming platforms like
        Crunchyroll, Funimation, or Hulu, where the Straw Hat Pirates'
        adventures unfold in all their glory!"
      </p>
    </div>
  
    <!-- Table with pictures and names -->
    <table id="characterTable">
      <tr id="characterRow"></tr>
    </table>
  
    <!-- Button for watching -->

  </div>

  <div class = "button-op">
    <a href="https://aniwave.to/watch/one-piece.ov8/ep-1" target="_blank">
        <button>Watch Now</button>
      </a>
  </div>
  