<script>
	// see: https://www.youtube.com/watch?v=Y6IbPfMU1xM
	import { i, languages, language, switchLanguage, referenceLanguage } from '@inlang/sdk-js';

console.log(`referenceLanguage: `, referenceLanguage)

	// Make this assignment to show correct select selection on refresh
	let selectedLang = 'de';
	// let selectedLang = language;

	const handleLanguageSelection = async (e) => {
		// console.log(`1. language = ${language} (vs. ${e.target.value})`)
		await switchLanguage(e.target.value);
	};
</script>

<h1>Test inlang JSON plugin</h1>

<nav>
	<ul id="nav-ul" style="height: 40px;">
		<!-- <li>
			<a href="https://www.wq-faq.com" target="_blank" rel="noopener noreferrer"
				><img id="recycle-drop-menu" src="/recycle-drop.png" alt="WQ | FAQ icon" /> WQ
				<span style="color: orange;">|</span> FAQ Blog</a
			>
		</li> -->
		<li>
			<div style="text-align: right; margin-right: 20px;">
				<select
					name="langs"
					id="langs"
					on:change={handleLanguageSelection}
					bind:value={selectedLang}
					style="text-align: {language === 'ar' || language === 'il' ? 'right' : 'left'};"
				>
					<option value="en">English</option>
					<option value="de">Deutsch</option>
					<!-- <option value="ar">اللغة العربية</option> -->
					<option value="fr">Français</option>
					<option value="es">Español</option>
					<!-- <option value="il">עִברִית</option> -->
					<option value="gr">Ελληνικά</option>
					<option value="br">Brasileiro</option>
					<option value="hi">हिंदी</option>
				</select>
			</div>
		</li>
		<!-- <li class="relative">
			{#if currentTheme == 'light'}
				<a class="moon" href={'#'} on:click={() => setTheme('dark')}>
					<Moon />
				</a>
			{:else}
				<a class="sun" href={'#'} on:click={() => setTheme('light')}>
					<Sun />
				</a>
			{/if}
		</li> -->
	</ul>
</nav>

<p>Here: {@html i('one-p1')} :erehT</p>
<p>Here: {i('one-p2')} :erehT</p>

<p>{language}</p>

{#each languages as lang}
  <p>{lang}</p>
{/each}

{@html i('block')}

<hr />
