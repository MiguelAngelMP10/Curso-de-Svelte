<script>
  //logica
  import Button from "./Button.svelte";

  let someText = "Estudiente de Platzi";
  let count = 0;
  let style = { darkMode: false };

  function handleClick() {
    count += 1;
  }

  function toggle() {
    style.darkMode = !style.darkMode;
    window.document.body.classList.toggle("dark-mode");
  }
</script>

<style>
  p {
    color: var(--theme-color);
  }
</style>

<div class="About">

  {#if !style.darkMode}
    <p>{someText}</p>
  {:else}
    <p>
      <span>Hello DarckMode</span>
    </p>
  {/if}

  <Button text="Click" {count} on:click={handleClick} />
  <Button text="DarkMode" on:click={toggle} />
</div>
