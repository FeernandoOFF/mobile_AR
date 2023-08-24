<script lang="ts">
	import '../app.css';
	import 'iconify-icon';
	import { fly } from 'svelte/transition';
	import { App } from 'konsta/svelte';
	import { onMount, tick } from 'svelte';
	export let data;
	let os: 'ios' | 'material' | 'parent' = 'ios';

	onMount(async () => {
		console.log(navigator.userAgent);
		await tick();
		if (/(Mac|iPhone|iPod|iPad)/i.test(navigator.userAgent) && !window.MSStream) {
			os = 'ios';
			console.log('mac');
		} else {
			os = 'material';
			console.log('other');
		}
	});
</script>

{#key data.url}
	<div in:fly={{ x: -200, duration: 150, delay: 120 }} out:fly={{ x: 200, duration: 150 }}>
		<App theme={os} safeAreas>
			<slot />
		</App>
	</div>
{/key}
