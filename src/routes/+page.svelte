<script>
  import Header from "../lib/Header.svelte";
  letet characters = [
    { name: "Shisui", info: "Uchiha clan member" },
    { name: "Madara", info: "Legendary Uchiha" },
    { name: "Itachi", info: "Prodigy Uchiha" },
    { name: "Naruto", info: "Hokage-to-be" },
    { name: "Minato", info: "Fourth Hokage" },
    { name: "Jiraiya", info: "Legendary Sannin" },
  ];
</script>

<Header />
<p>These are the some of the most liked Naruto characters</p>

<div class="parent">
  
  {#each buttons as button (button)}
    <div class="child">
      <button class={`image-button ${button}`}></button>
    </div>
  {/each}
</div>
