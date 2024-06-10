<script lang="ts">
	import Events from './Events.svelte';
	import Message from './Message.svelte';

	let { ...restProps } = $props();
</script>

<Events
	{...restProps}
>
	{#snippet children(events)}
		{#each events as event (event.id)}
			{#if event.type === 'message'}
				<Message {...event} />
			{/if}
		{/each}
	{/snippet}
</Events>
