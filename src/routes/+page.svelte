<script>
	import { Grid, Container, Button, Group, NativeSelect, Modal, Badge } from '@svelteuidev/core';
	import { Person, Stack } from 'radix-icons-svelte';
	let opened = false;
</script>

<Group position="center" class="mb-5">
	<Button on:click={() => (opened = true)} color="red">
		<i class="fa-solid fa-user" slot="leftIcon" />
		Author
	</Button>
	<Button on:click={() => (opened = true)} color="red">
		<i class="fa-solid fa-layer-group" slot="leftIcon" />
		Type
	</Button>
	<Button on:click={() => (opened = true)} color="red">
		<i class="fa-solid fa-tag text-white" slot="leftIcon" />
		Tags
	</Button>
</Group>

<Group position="center" class="mb-5">
	<Badge>Popular last 7 days</Badge>
</Group>

<Group position="center">
	{#each Array(30) as _}
		<div class="bg-red-500 h-72 w-72">A</div>
	{/each}
</Group>

<Modal {opened} on:close={() => (opened = false)} title="Introduce yourself!">Hello World!</Modal>
