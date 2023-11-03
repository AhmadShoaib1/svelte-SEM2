<script>
  import Header from "../lib/Header.svelte";
  let characters = [
    { name: "Shisui", info: "Uchiha clan member" },
    { name: "Madara", info: "Legendary Uchiha" },
    { name: "Itachi", info: "Prodigy Uchiha" },
    { name: "Naruto", info: "Hokage-to-be" },
    { name: "Minato", info: "Fourth Hokage" },
    { name: "Jiraiya", info: "Legendary Sannin" },
  ];
  let flipped = Array(characters.length).fill(false);

  function toggleFlip(index) {
    flipped[index] = !flipped[index];
  }
</script>

<Header />
<div class="parent">
  {#each characters as { name, info }, index (name)}
    <div
      class="child"
      on:mouseenter={() => toggleFlip(index)}
      on:mouseleave={() => toggleFlip(index)}
      on:focus={() => toggleFlip(index)}
      on:blur={() => toggleFlip(index)}
      tabindex="0"
      role="button"
    >
      {#if flipped[index]}
        <div class="image-container flipped">
          <div class="front">
            <img src={`../img/${name.toLowerCase()}.jpg`} alt={name} />
          </div>
          <div class="back">
            <p>{info}</p>
          </div>
        </div>
      {:else}
        <div class="image-container">
          <div class="front">
            <img src={`../img/${name.toLowerCase()}.jpg`} alt={name} />
          </div>
          <div class="back">
            <p>{info}</p>
          </div>
        </div>
      {/if}
    </div>
  {/each}
</div>
