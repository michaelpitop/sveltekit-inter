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

<div class="container">
  {#if $isLocaleLoaded}
    
    <div>
      <button on:click={handleLocaleChange} value="en">English</button>
      <button on:click={handleLocaleChange} value="de">Deutsch</button>
    </div>

  {:else}
    <div class="container__content">Locale initializing...</div>
  {/if}
</div>

