<script>
  import {onMount} from 'svelte';
  import {getSupportedLanguages, i18n, setLanguage} from 'web-translate';

  let languageCode = 'en';
  let languages = {};

  onMount(async () => {
    languages = await getSupportedLanguages();
  });

  async function changeLanguage(event) {
    const code = event.target.value;
    await setLanguage(code);
    // Don't set this until after web-translate knows the new code.
    languageCode = code;
  }
</script>

<h1>web-translate Demo</h1>

<select on:change={changeLanguage}>
  {#each Object.keys(languages).sort() as name}
    <option value={languages[name]}>{name}</option>
  {/each}
</select>

{#key languageCode}
  <p>Greeting is {i18n('hello')}.</p>
{/key}
