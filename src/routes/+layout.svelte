<script lang="ts">
	import '../app.scss';
	import Title from '$lib/components/Title.svelte';
	import { Hamburger } from 'svelte-hamburgers';

	let open;
	let bookmarks = false;
	let fullUrls = true;

	const profileRadioValue = 'benoit';
</script>

<Title></Title>

{#if open}
	<!-- show menu -->
{/if}
<slot />

<style></style>
