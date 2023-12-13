<script lang="ts">
  import { goto } from '$app/navigation';
	import { isLocaleLoaded } from '$lib/i18n';
  import { _, locale, locales } from 'svelte-i18n';

  let value: string = 'en';

  function handleLocaleChange(event: any) {
    event.preventDefault();
    value = event?.target?.value;
    $locale = value;
    goto('/home');
  }
</script>

<div class="buttons-div" >
  {#if $isLocaleLoaded}
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <div  class="lang-container">
    
      <button on:click={handleLocaleChange} value="en">English</button>
      <button on:click={handleLocaleChange} value="de">Deutsch</button>
      
    </div>

  {:else}
    <div class="container__content">Locale initializing...</div>
  {/if}
</div>

<style>
  .buttons-div {
    width: 100%;
    height: 100%;
  }

  .lang-container  {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;

  }
  button {
    border: none;
    color: black;
    padding: 16px 32px;
    text-align: center;
    font-size: 100px;
    margin: 4px 2px;
    transition: 0.3s;
    opacity: 0.7;
    display: inline-block;
    text-decoration: none;
    cursor: pointer;   
    border-radius: 15%; 
  }
  button:hover {
    outline-color: transparent;
    outline-style:solid;
    box-shadow: 0 0 0 4px #5a01a7;
    transition: 0.7s;
  }
</style>