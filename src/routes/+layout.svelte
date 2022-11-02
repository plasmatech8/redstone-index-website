<script>
	import '../app.css';
	import {
		SvelteUIProvider,
		fns,
		AppShell,
		Navbar,
		Header,
		Title,
		Divider
	} from '@svelteuidev/core';
	import { isDarkTheme } from '$lib/stores';

	function toggleTheme() {
		$isDarkTheme = !$isDarkTheme;
	}
</script>

<SvelteUIProvider
	ssr
	withNormalizeCSS
	withGlobalStyles
	themeObserver={$isDarkTheme ? 'dark' : 'light'}
>
	<AppShell>
		<Header slot="header" height="100">
			<nav class="flex bg-yellow-500">
				<!-- left -->
				<div class="bg-red-500">Left</div>
				<div>Middle</div>
				<div>Right</div>
			</nav>
		</Header>
		<slot>This is the main content</slot>
	</AppShell>
</SvelteUIProvider>
