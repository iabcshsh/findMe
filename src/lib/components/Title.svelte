<script lang="ts">
	import { AspectRatio } from '$lib/components/ui/aspect-ratio';
	import { Hamburger } from 'svelte-hamburgers';
	export let open;
</script>

<div class="m-4 flex justify-between">
	<div class="flex items-center space-x-4">
		<div class="w-14">
			<AspectRatio ratio={16 / 16} class="">
				<img src="favicon.png" alt="Missing" class="rounded-md object-cover" />
			</AspectRatio>
		</div>
		<!-- <h1 class="m-1 font-sans text-4xl font-bold">Missing</h1> -->
	</div>

	<Hamburger bind:open />
</div>
