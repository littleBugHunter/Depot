<script>
  export let data;
  let showDialog = false;
  function openDialog() {
    showDialog = true;
  }
  function closeDialog() {
    showDialog = false;
  }
</script>

<div>
  <textarea bind:value={data} />
  <br />
  <button on:click={openDialog} class="sheetButton fullHeight"> Edit </button>
</div>
<!-- show dialg if useDialog is true -->
{#if showDialog}
  <div
    style="
    position: fixed;
    background-color: rgba(0,0,0,0.8);
    width: 100vw;
    height:  100vh;
    left: 0;
    top: 0;
    z-index: 0;
"
  />
  <dialog id="textDialog" open>
    <textarea bind:value={data} />
    <button on:click={closeDialog} class="sheetButton fullWidth"> Ok </button>
  </dialog>
{/if}

<style>
    textarea {
        padding: 5px 5px 5px 5px;
        /* margin: 5px; */
        box-sizing: border-box;
        -webkit-box-sizing:border-box;
        -moz-box-sizing: border-box;
        font-size: 13px;
				border: 1px solid var(--vscode-input-border);
        background-color: var(--vscode-input-background);
        color: var(--vscode-input-foreground);
        width: 100%;
        height: 100%;
    }
</style>
==== BASE ====
