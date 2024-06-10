<script lang="ts">
  type ChannelEvent = {
    id: string,
    text: string,
    type: 'message' | 'other',
  }

	type Events = ChannelEvent[];

	type Props = {
		children: Snippet<[Events]>;
	};

	// Props
	let { children, ...renderProps }: Props = $props();

	// State
	let events: Events = $state([
    {id: '0', text: 'hello', type: 'message'},
    {id: '1', type: 'other'},
    {id: '2', text: 'how are you?', type: 'message'}
  ]);

</script>

<div>
	{@render children(events)}
</div>
