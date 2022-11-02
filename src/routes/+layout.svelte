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
			<nav class="flex flex-wrap container mx-auto p-3 h-full">
				<!-- left -->
				<div class="w-1/2 h-full md:w-1/3 text-white">
					<h1>Redstone Index</h1>
				</div>
				<!-- right -->
				<div class="w-1/2 h-full md:order-3 md:w-1/3 flex justify-end">
					<Button class="h-full text-white" variant="subtle">
						<Cube slot="leftIcon" />
						Builds
					</Button>
					<Button class="h-full text-white" variant="subtle">
						<Person slot="leftIcon" />
						Sign Up
					</Button>
				</div>
				<!-- middle -->
				<div class="w-full md:w-1/3">
					<form on:submit|preventDefault class="flex h-full">
						<input
							type="search"
							name=""
							id=""
							class="h-full w-full p-2 pl-7 bg-red-700 rounded-l-md outline-none placeholder:text-gray-300 text-md text-white"
							placeholder="Search Redstone Index"
						/>
						<button class="h-full w-10 grid place-items-center bg-red-700 rounded-r-md">
							<MagnifyingGlass class="text-white" size={23} />
						</button>
					</form>
				</div>
			</nav>
		</Header>
		<slot>This is the main content</slot>
	</AppShell>
</SvelteUIProvider>
