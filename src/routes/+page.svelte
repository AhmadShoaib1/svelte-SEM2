<script>
  import Header from "../lib/Header.svelte";
  let characters = [
    { name: "Shisui", info: "Shisui Uchiha, a shadow among shadows, his eyes echoing the silent whispers of a legacy written in the ethereal ink of the Uchiha clan."},
    { name: "Madara", info: "Madara Uchiha, a titan in the tumultuous realm of shinobi, carved his name in history with the indelible strokes of ambition, weaving a tapestry of power and chaos across the ninja world." },
    { name: "Itachi", info: "Itachi Uchiha, a shadow veiled in sacrifice, navigated the labyrinth of darkness to protect the very village that condemned him. His eyes mirrored both tragedy and redemption, leaving an eternal mark on the canvas of ninja lore" },
    { name: "Naruto", info: "Naruto Uzumaki, a spirited hurricane of resilience, carved his legacy with dreams as vast as the Hokage mountain. From the shadows of loneliness, he emerged into a radiant sun, uniting a fractured world with bonds forged in the crucible of his unwavering spirit." },
    { name: "Minato", info: "Fourth Hokage" },
    { name: "Jiraiya", info: "Legendary Sannin" },
  ];
  let flipped = Array(characters.length).fill(false);

  function toggleFlip(index) {
    flipped[index] = !flipped[index];
  }
</script>


<p>these are the most liked Naruto characters</p>
<div class="parent">
  {#each characters as { name, info, link }, index (name)}
    <a
      href={link}
      class="child"
      on:mouseenter={() => toggleFlip(index)}
      on:mouseleave={() => toggleFlip(index)}
      on:focus={() => toggleFlip(index)}
      on:blur={() => toggleFlip(index)}
      tabindex="0"
    >
      <div class="image-container" class:flipped={flipped[index]}>
        <div class="front">
          <img src={`../img/${name.toLowerCase()}.jpg`} alt={name} />
        </div>
        <div class="back">
          <p>{info}</p>
        </div>
      </div>
    </a>
  {/each}
</div>
