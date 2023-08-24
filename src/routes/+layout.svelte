<script lang="ts">
	import { fly } from 'svelte/transition';
	import '../app.css';
	import { App } from 'konsta/svelte';
	import { onMount } from 'svelte';
	export let data;
	let os: 'ios' | 'material' | 'parent';

	onMount(() => {
		if (/(Mac|iPhone|iPod|iPad)/i.test(navigator.userAgent) && !window.MSStream) {
			os = 'ios';
		} else {
			os = 'material';
		}
	});
</script>

{#key data.url}
	<div in:fly={{ x: -200, duration: 150, delay: 120 }} out:fly={{ x: 200, duration: 150 }}>
		<App theme={os}>
			<slot />
		</App>
	</div>
{/key}
