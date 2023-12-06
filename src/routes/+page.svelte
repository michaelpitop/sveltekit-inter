<script lang="ts">
	import { isLocaleLoaded } from '$lib/i18n';
  import { _, locale, locales } from 'svelte-i18n';

  let value: string = 'en';

  function handleLocaleChange(event: any) {
    event.preventDefault();
    value = event?.target?.value;
    $locale = value;
  }
</script>

<div class="container">
  {#if $isLocaleLoaded}
    <div class="container__title">
      <h1>{$_('title')}</h1>
    </div>
    <div class="container__toggle">
      <span>{$_('toggle_label')} </span>
      <select {value} on:change={handleLocaleChange}>
        <option value="en" selected>English</option>
        <option value="de">German</option>
      </select>

    </div>

  {:else}
    <div class="container__content">Locale initializing...</div>
  {/if}
</div>
