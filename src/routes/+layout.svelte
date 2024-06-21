<script lang="ts">
	import '../app.scss';
	import Title from '$lib/components/Title.svelte';
	import Menu from '$lib/components/Menu.svelte';
	import { Hamburger } from 'svelte-hamburgers';

	let open = true;
	let bookmarks = false;
	let fullUrls = true;

	const profileRadioValue = 'benoit';
</script>

<Title {open}></Title>

{#if open}
	<!-- show menu -->
	<Menu />
{/if}
<slot />

<style></style>
