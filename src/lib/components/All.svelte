<script>
	import GridGallery from './GridGallery.svelte';
	let rows = 6;
	let cols = 6;
	let growX = 7;
	let growY = 2;
	let duration = 600;
	let activeClassName = 'GridGalleryActiveItem';
	$: cs = Array(rows * cols);
</script>

Rows: <input type="number" bind:value={rows} style="width:3rem" />
Cols: <input type="number" bind:value={cols} style="width:3rem" />
GrowX: <input type="number" bind:value={growX} style="width:3rem" />
GrowY: <input type="number" bind:value={growY} style="width:3rem" />
<GridGallery class="gg" {growX} {growY} {rows} {cols} {duration} {activeClassName}>
	{#each cs as c, ix}
		<div
			class="c"
			style="position:relative;background-image:url(https://loremflickr.com/{610 + ix}/{610 +
				ix}/rio)"
		>
			<span
				style="position:absolute; bottom:0; left:0; width:100%; color:white; filter: drop-shadow(2px 4px 6px black);"
				><center>
					Image {ix + 1}
				</center></span
			>
		</div>
	{/each}
</GridGallery>

<style>
	.c {
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center;
		transition: all 600ms;
	}

	:global(.gg) {
		height: calc(100% - 3rem);
	}
	/*
	:global(.GridGalleryActiveItem){
		border: solid 1px white !important;
	}
	*/
</style>
