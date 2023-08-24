<script>
	import { Dialog, DialogButton, Page, Preloader } from 'konsta/svelte';
	import { onMount } from 'svelte';
	let dialog = false;
	let box = '#4CC3D9';
	let sphere = '#EF2D5E';
	let cylinder = '#FFC65D';
</script>

{#await import('aframe')}
	<div class="h-screen grid place-items-center">
		<Preloader size="w-30 h-30" />
	</div>
{:then aframe}
	<a-scene
		arjs
		embedded
		class=" h-auto w-full aspect-square max-h-[400px] rounded-full mx-auto border-4 border-green-400 overflow-hidden max-w-sm"
	>
		<a-entity camera />
		<a-box position="-1 0.5 -3" rotation="0 45 0" color={box} shadow />
		<a-marker preset="hiro">
			<a-box position="0 0.5 0" material="color: yellow;" />
		</a-marker>
		<a-sphere
			position="0 1.25 -5"
			radius="1.25"
			color={sphere}
			shadow
			on:click={() => (dialog = true)}
		/>
		<a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color={cylinder} shadow />
		<a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4" shadow />
	</a-scene>
{:catch error}
	<p>Something went wrong</p>
{/await}
