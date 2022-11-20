<script lang="ts">
	import { Badge, Card, Group, Text, Center } from '@svelteuidev/core';
	import { useId } from '@svelteuidev/composables';
	import { shuffle } from 'lodash';

	const tags = shuffle([
		'wireless redstone',
		'0-tick pulse',
		'ender-pearl stasis',
		'monostable circuit',
		'flying machine',
		'slime block',
		't-flip flop',
		'chunk loader',
		'door',
		'bedrock-breaker',
		'instant redstone',
		'computer'
	]).splice(0, Math.floor(Math.random() * 10 + 2));
</script>

<Card p="xs" class="h-96 w-full">
	<!-- Top -->
	<Group position="apart" class="mb-2">
		<Text weight="bold">Build Title</Text>
		<Group position="apart">
			<Text size="xs">By <a href="/user/plasmatech8" class="underline">plasmatech8</a></Text>
			<img
				src="https://i.pravatar.cc/300?{useId()}"
				alt="user avatar"
				class="rounded-full w-10 h-10"
			/>
		</Group>
	</Group>
	<!-- Image -->
	<Card.Section padding="lg" class="mb-1">
		<img
			src="https://source.unsplash.com/random/?build&{useId()}"
			alt="build"
			class="object-cover h-64 w-full"
		/>
	</Card.Section>
	<!-- Bottom -->
	<div class="fade-bottom h-16">
		<Center inline>
			<Group position="left" spacing={4} align="center">
				{#each tags as tag}
					<Badge>{tag}</Badge>
				{/each}
			</Group>
		</Center>
	</div>
</Card>

<style>
	.fade-bottom {
		mask-image: linear-gradient(to bottom, black calc(100% - 10px), transparent 100%);
	}
</style>
