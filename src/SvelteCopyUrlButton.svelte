<script>
function copy() {
  if (!window.getSelection) {
    alert("Please copy the URL from the location bar.");
    return;
  }
  const placeholder = document.createElement("p");
  placeholder.textContent = url ? url : window.location.href;
  placeholder.style.cssText = "z-index:-9;position:relative";
  document.body.appendChild(placeholder);

  const range = document.createRange();
  range.setStartBefore(placeholder);
  range.setEndAfter(placeholder);

  const selection = window.getSelection();
  selection.removeAllRanges();
  selection.addRange(range);

  document.execCommand("copy");
  document.body.removeChild(placeholder);

  copied = true;
  setTimeout(function () {
    copied = false;
  }, timeout);
}
let copied = false;
export let defaultText = "Copy Url";
export let copiedText = "Copied!";
export let size = 14;
export let icon = false;
export let timeout = 1000;
export let styled = true;
export let url;
</script>

<button
  style="--scu-size: {size}px"
  on:click="{copy}"
  class="{$$props.class} scu-button"
  class:scub-styled="{styled === true}"
>
  {#if !copied}
    <svg class="scu-button--icon" viewBox="0 0 16 14" aria-hidden="true"><path
        fill-rule="evenodd"
        d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"
      ></path></svg>
    {#if icon == false}
      <span class="scu-button--content">{defaultText}</span>
    {/if}
  {:else}
    <svg
      class="scu-button--icon"
      viewBox="0 0 512 512"
      style="enable-background:new 0 0 512 512;"
      xml:space="preserve"
    >
      <path
        d="M504.502,75.496c-9.997-9.998-26.205-9.998-36.204,0L161.594,382.203L43.702,264.311c-9.997-9.998-26.205-9.997-36.204,0
          c-9.998,9.997-9.998,26.205,0,36.203l135.994,135.992c9.994,9.997,26.214,9.99,36.204,0L504.502,111.7
          C514.5,101.703,514.499,85.494,504.502,75.496z"
      ></path>
    </svg>
    {#if icon == false}
      <span class="scu-button--content">{copiedText}</span>
    {/if}
  {/if}
</button>

<style>
.scu-button {
  outline: none;
  border: none;
  background: none;
  color: inherit;
  font-family: inherit;
  font-size: var(--scu-size);
  transition: all 120ms ease-out;
}
.scu-button svg {
  width: var(--scu-size);
  height: var(--scu-size);
}
</style>
