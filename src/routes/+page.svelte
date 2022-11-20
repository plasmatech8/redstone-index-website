<script>
	import BuildCard from '$lib/BuildCard.svelte';
	import { Button, Group, Modal, Badge } from '@svelteuidev/core';
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

<Group position="center" align="baseline">
	{#each Array(30) as _}
		<div class="w-96">
			<BuildCard />
		</div>
	{/each}
</Group>

<Modal {opened} on:close={() => (opened = false)} title="Introduce yourself!">Hello World!</Modal>
