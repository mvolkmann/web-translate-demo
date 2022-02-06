<script>
	import { getLanguageCode, i18n, setLanguage } from 'web-translate';

	let languageCode = 'en';

	changeLanguage('es');

	async function changeLanguage(code) {
		await setLanguage(code);
		languageCode = code;
	}
</script>

<h1>Welcome to web-translate</h1>

{#key languageCode}
	<p>Language is {languageCode}</p>
	<p>Greeting is {i18n('hello')}.</p>
{/key}
