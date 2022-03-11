<script>
  import BoxShadow from './components/BoxShadow.svelte'
  import BorderRadius from './components/BorderRadius.svelte'

  let boxShadow = true
  let borderRadius = false

  function toggle(e) {
    const elem = e.currentTarget
    const btnText = elem.innerText
    console.log(btnText)
    if (btnText === 'Box Shadow') {
      boxShadow = true
      borderRadius = false
    } else if (btnText === 'Border Radius') {
      boxShadow = false
      borderRadius = true
    }
  }
</script>

<div class="btn-group">
  <button on:click={toggle}>Box Shadow</button>
  <button on:click={toggle}>Border Radius</button>
</div>

<div>
  {#if boxShadow}
    <BoxShadow />
  {:else if borderRadius}
    <BorderRadius />
  {/if}
</div>
