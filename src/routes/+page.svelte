<script>
  import Header from "../lib/Header.svelte";
  let buttons = [
    "first-button",
    "second-button",
    "third-button",
    "fourth-button",
    "fifth-button",
    "sixth-button"
  ];
</script>

<Header />

<div class="parent">
  {#each buttons as button (button)}
    <div class="child">
      <button class={`image-button ${button}`}></button>
    </div>
  {/each}
</div>
