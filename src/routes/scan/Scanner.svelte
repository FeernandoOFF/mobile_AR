<script lang="ts">
	import { Dialog, DialogButton, Page, Preloader } from 'konsta/svelte';
	import { onMount } from 'svelte';

	let videoCamerae: HTMLVideoElement;
	onMount(() => {
		const constraints = {
			video: true
		};
		// when you grab the stream - display it on the <video> element
		navigator.mediaDevices.getUserMedia(constraints).then((stream) => {
			videoCamerae.srcObject = stream;
		});
	});
</script>

{#await import('aframe')}
	<div class="h-screen grid place-items-center">
		<Preloader size="w-30 h-30" />
	</div>
{:then aframe}
	<div
		class="relative h-auto w-full aspect-square max-h-[400px] rounded-full mx-auto border-4 border-green-400 overflow-hidden max-w-sm"
	>
		<video bind:this={videoCamerae} class="w-full aspect-square h-auto absolute" autoplay />
		<a-scene embedded class="absolute">
			<a-entity camera />
			<a-box position="-1 0.5 -3" rotation="0 45 0" color={'#EF2D5E'} shadow />
			<a-marker preset="hiro">
				<a-box position="0 0.5 0" material="color: yellow;" />
			</a-marker>
			<a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E" shadow />
			<a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4" shadow />
		</a-scene>
	</div>
{/await}
