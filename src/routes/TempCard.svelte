<script>
	import { Card, Text, Badge, Group } from '@svelteuidev/core';
</script>

<Card p="lg">
	<Card.Section padding="lg">
		<img
			src="https://images.unsplash.com/photo-1555881400-74d7acaacd8b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=3540&q=80"
			height={160}
			alt="Portugal"
		/>
	</Card.Section>
	<Group position="apart">
		<Text weight={500}>Portugal Porto Adventures</Text>
		<Badge color="pink" variant="light">On Sale</Badge>
	</Group>
	<Text size="sm">
		With Portugal Porto Adventures you can explore more of the beautiful portuguese cities, by
		walking on food, meeting the locals and eat excellent food and wine
	</Text>
</Card>
