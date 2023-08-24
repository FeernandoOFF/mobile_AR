<script>
	import { Dialog, DialogButton, Page, Preloader } from 'konsta/svelte';
	import { onMount } from 'svelte';
	let aframe = false;
	let mindar = false;
	let dialog = false;
	let box = '#4CC3D9';
	let sphere = '#EF2D5E';
	let cylinder = '#FFC65D';
</script>

<svelte:head>
	<script
		src="https://aframe.io/releases/1.4.2/aframe.min.js"
		on:load={() => (aframe = true)}
	> </script>
	<script
		src="https://cdn.jsdelivr.net/npm/mind-ar@1.2.2/dist/mindar-image-aframe.prod.js"
		on:load={() => (mindar = true)}
	></script>
</svelte:head>

{#if aframe && mindar}
	<a-scene
		mindar-image="imageTargetSrc: https://cdn.jsdelivr.net/gh/hiukim/mind-ar-js@1.2.2/examples/image-tracking/assets/card-example/card.mind; uiError:no; uiLoading: no; uiScanning: no"
		color-space="sRGB"
		renderer="colorManagement: true, physicallyCorrectLights"
		vr-mode-ui="enabled: false"
		device-orientation-permission-ui="enabled: false"
		embedded
		class=" h-auto w-full aspect-square max-h-[400px] rounded-full mx-auto border-4 border-green-400 overflow-hidden max-w-sm"
	>
		<a-assets>
			<img
				id="card"
				src="https://cdn.jsdelivr.net/gh/hiukim/mind-ar-js@1.2.2/examples/image-tracking/assets/card-example/card.png"
			/>
			<a-asset-item
				id="avatarModel"
				src="https://cdn.jsdelivr.net/gh/hiukim/mind-ar-js@1.2.2/examples/image-tracking/assets/card-example/softmind/scene.gltf"
			/>
		</a-assets>

		<a-camera position="0 0 0"  />
		<a-entity mindar-image-target="targetIndex: 0">
			<a-plane src="#card" position="0 0 0" height="0.552" width="1" rotation="0 0 0" />
			<a-gltf-model
				rotation="0 0 0 "
				position="0 0 0.1"
				scale="0.005 0.005 0.005"
				src="#avatarModel"
				animation="property: position; to: 0 0.1 0.1; dur: 1000; easing: easeInOutQuad; loop: true; dir: alternate"
			/></a-entity
		>
		<a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color={cylinder} shadow />
		<a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4" shadow />
	</a-scene>
{:else}
	<div class="h-screen grid place-items-center">
		<Preloader size="w-30 h-30" />
	</div>
{/if}
