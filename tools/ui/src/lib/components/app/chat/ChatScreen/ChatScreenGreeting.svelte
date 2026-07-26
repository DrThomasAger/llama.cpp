<script lang="ts">
	import { serverStore } from '$lib/stores/server.svelte';

	interface Props {
		isEmpty: boolean;
	}

	let { isEmpty = false }: Props = $props();
</script>

<div
	class={[
		'pointer-events-none mb-4 hidden px-4 text-center text-balance',
		isEmpty && 'mb-[calc(50dvh-8rem)] md:mb-6 pointer-events-auto block!'
	]}
>
	<!-- smile-lens branch: the left-facing "(:|" drawn in the text color,
	     a doorway to the Smile repository -->
	<h1 class="mb-2 text-2xl font-semibold tracking-tight md:text-3xl">
		<a
			href="https://github.com/DrThomasAger/Smile"
			target="_blank"
			rel="noopener"
			title="Smile on GitHub"
			aria-label="Smile on GitHub"
			style="display:inline-block;width:1em;height:1em;vertical-align:-0.1em;background:currentColor;-webkit-mask:url(/greeting-smile.svg) center/contain no-repeat;mask:url(/greeting-smile.svg) center/contain no-repeat;"
		></a> Smile Chat!
	</h1>

	<p class="text-muted-foreground md:text-lg">
		{serverStore.props?.modalities?.audio ? 'Record audio, type a message ' : 'Type a message'} or upload
		files to get started
	</p>
</div>
