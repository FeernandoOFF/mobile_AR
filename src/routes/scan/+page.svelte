<script>
	import { Block, Card, Navbar, NavbarBackLink, Page } from 'konsta/svelte';
	import Scanner from './Scanner.svelte';
</script>

<Page>
	<Navbar title="Scan your content">
		<NavbarBackLink slot="left" text="Back" onClick={() => history.back()} />
	</Navbar>
	<div class="my-10">
		<Scanner />
	</div>

	<Block>
		<Card class="w-full max-w-md mx-auto">
			<h2 slot="header">Scan the front of the box</h2>
			<p>Please scan all 6 sides of the packaging as displayed on the instructions bellow:</p>
			<picture>
				<img
					src="/assets/medicine.png"
					alt="First step, scan the front of the box"
					class="mx-auto max-w-[120px] w-full my-4"
				/>
			</picture>
		</Card>
	</Block>
</Page>
