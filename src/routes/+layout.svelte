<script>
	import '../app.css';
	import {
		SvelteUIProvider,
		fns,
		AppShell,
		Navbar,
		Header,
		Title,
		Divider,
		TextInput,
		Button
	} from '@svelteuidev/core';
	import { isDarkTheme } from '$lib/stores';
	import { MagnifyingGlass, Person, Cube } from 'radix-icons-svelte';
	import '@fortawesome/fontawesome-free/js/all.min.js';

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
		<Header slot="header" height="" class="bg-red-500">
			<nav class="flex flex-wrap container mx-auto p-3 h- gap-2 md:gap-0 items-center">
				<!-- left -->
				<div class="h-full text-white flex-grow">
					<a href="/">
						<h1 class="select-none">Redstone Index</h1>
					</a>
				</div>
				<!-- right -->
				<div class="h-full md:order-3 flex justify-end align-middle flex-grow gap-6">
					<Button color="red">
						<Cube slot="leftIcon" size={20} />
						Builds
					</Button>
					<Button color="red">
						<Person slot="leftIcon" size={20} />
						Sign In
					</Button>
				</div>
				<!-- middle -->
				<div class="w-full md:w-auto flex-grow">
					<form on:submit|preventDefault class="flex h-full">
						<input
							type="search"
							name=""
							id=""
							class="h-9 w-full p-2 pl-7 bg-red-700 rounded-l-md outline-none placeholder:text-gray-300 text-md text-white"
							placeholder="Search Redstone Index"
						/>
						<button class="h-9 w-10 grid place-items-center bg-red-700 rounded-r-md">
							<MagnifyingGlass class="text-white" size={23} />
						</button>
					</form>
				</div>
			</nav>
		</Header>
		<slot>This is the main content</slot>
	</AppShell>
</SvelteUIProvider>
