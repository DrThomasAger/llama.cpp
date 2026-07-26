<script lang="ts">
	import { Logo } from '$lib/components/app';
	import { fade } from 'svelte/transition';

	interface Props {
		class?: string;
		message?: string;
	}

	// smile-lens branch: the connection screen is the Smile Chat logo
	// alone - no text, no status, nothing else. `message` is still
	// accepted so callers need not change, but it is not shown.
	let { class: className = '', message: _message = '' }: Props = $props();
</script>

<div class="flex h-full items-center justify-center {className}">
	<div class="animate-pulse" in:fade={{ duration: 300 }}>
		<Logo style="--size: 6rem" />
	</div>
</div>
