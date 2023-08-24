<script>
	import {
		Page,
		Navbar,
		Block,
		Fab,
		Button,
		List,
		ListItem,
		BlockTitle,
		Card,
		Icon
	} from 'konsta/svelte';
</script>

<Page>
	<Navbar title="Check your med" />
	<Block class="bg-green-400 my-0 h-[20vh] grid place-items-end p-0">
		<Card header="Scan your product" class="m-0 translate-y-8 mx-auto">
			<div class="flex gap-2">
				<p>Scan your product or enter serial code manually</p>
				<div>
					<a href="/scan">
						<Icon class="p-2 rounded-full grid place-items-center bg-green-800 text-lg">
							<iconify-icon icon="ic:round-chevron-right" slot="ios" />
							<iconify-icon icon="ic:sharp-chevron-right" slot="material" />
						</Icon>
					</a>
				</div>
			</div>
		</Card>
	</Block>
	<div class="mt-14">
		<BlockTitle>Navigation</BlockTitle>
		<List>
			<ListItem title="Scan now" href="/scan" />
			<ListItem title="History" href="/history" />
		</List>
		<Fab
			class="fixed left-1/2 bottom-4-safe transform -translate-x-1/2 z-20 grid place-items-center"
			href="/scan"
			><iconify-icon icon="jam:qr-code" slot="icon" class="grid" />
		</Fab>
	</div>
</Page>
