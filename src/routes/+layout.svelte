<script lang="ts">
	import { fly } from 'svelte/transition';
	import '../app.css';
	import { App } from 'konsta/svelte';
	export let data;
</script>

{#key data.url}
	<div in:fly={{ x: -200, duration: 200, delay: 200 }} out:fly={{ x: 200, duration: 200 }}>
		<App theme="ios">
			<slot />
		</App>
	</div>
{/key}
