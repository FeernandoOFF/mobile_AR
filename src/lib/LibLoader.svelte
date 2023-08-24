<script lang="ts">
	import { onMount, createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();
	export let url: string;
	let script: any;

	onMount(async () => {
		script.addEventListener('load', () => {
			dispatch('loaded');
		});

		script.addEventListener('error', (event: ErrorEvent) => {
			console.error('something went wrong', event);
			dispatch('error');
		});
	});
</script>

<svelte:head>
	<script bind:this={script} src={url}></script>
</svelte:head>
