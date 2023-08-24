<script>
	import { Dialog, DialogButton, Page } from 'konsta/svelte';
	import { onMount } from 'svelte';
	let dialog = false;
	let box = '#4CC3D9';
	let sphere = '#EF2D5E';
	let cylinder = '#FFC65D';
</script>

<Page>
	<Dialog opened={dialog} onBackdropClick={() => (dialog = false)}>
		<svelte:fragment slot="title">Konsta UI</svelte:fragment>
		Hello world!
		<svelte:fragment slot="buttons">
			<DialogButton onClick={() => (dialog = false)}>Ok</DialogButton>
		</svelte:fragment>
	</Dialog>

	{#await import('aframe')}
		<div class="h-screen grid place-items-center">
			<p class="text-4xl font-semibold">Loading...</p>
		</div>
	{:then aframe}
		<main class="">
			<div class="controls">
				<label>
					<input type="color" bind:value={box} />
					box
				</label>
				<label>
					<input type="color" bind:value={sphere} />
					sphere
				</label>
				<label>
					<input type="color" bind:value={cylinder} />
					cylinder
				</label>
			</div>
			<a-scene background="color: #FAFAFA">
				<a-entity camera />
				<a-box position="-1 0.5 -3" rotation="0 45 0" color={box} shadow />
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
		</main>
	{:catch error}
		<p>Something went wrong</p>
	{/await}
</Page>

<style>
	.controls {
		position: absolute;
		top: 1em;
		left: 1em;
		z-index: 2;
	}

	input {
		height: 2em;
	}
</style>
