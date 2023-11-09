<script>

  let characters = [
    { name: "Shisui", info: "Shisui Uchiha, a shadow among shadows, his eyes echoing the silent whispers of a legacy written in the ethereal ink of the Uchiha clan.", link: "https://www.google.com/search?q=shisui+uchiha" },
    { name: "Madara", info: "Madara Uchiha, a titan in the tumultuous realm of shinobi, carved his name in history with the indelible strokes of ambition, weaving a tapestry of power and chaos across the ninja world.", link: "https://www.google.com/search?q=madara+uchiha"  },
    { name: "Itachi", info: "Itachi Uchiha, a shadow veiled in sacrifice, navigated the labyrinth of darkness to protect the very village that condemned him. His eyes mirrored both tragedy and redemption, leaving an eternal mark on the canvas of ninja lore", link: "https://www.google.com/search?q=itachi+uchiha" },
    { name: "Naruto", info: "Naruto Uzumaki, a spirited hurricane of resilience, carved his legacy with dreams as vast as the Hokage mountain. From the shadows of loneliness, he emerged into a radiant sun, uniting a fractured world with bonds forged in the crucible of his unwavering spirit." , link: "https://www.google.com/search?q=naruto+uzumaki"},
    { name: "Minato", info: "Minato Namikaze, the Flash of the Hidden Leaf, left an indelible mark on history with his unparalleled speed and unyielding love. As the Fourth Hokage, he soared through challenges, leaving a legacy of sacrifice and a flicker of hope in the hearts of those who remember the Yellow Flash." , link: "https://www.google.com/search?q=minato+namikaze"},
    { name: "Jiraiya", info: "Jiraiya, the Toad Sage, navigated the pages of both epic tales and turbulent times. With his wit, charisma, and unyielding spirit, he etched his name in the annals of ninja history. Whether chronicling adventures or facing adversaries, Jiraiya's legacy continues to ripple through the ninja world." , link: "https://www.google.com/search?q=jiraiya+"},
  ];
  let flipped = Array(characters.length).fill(false);

  function toggleFlip(index) {
    flipped[index] = !flipped[index];
  }
</script>
link: "/../img/jiraiya.jpg"


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
