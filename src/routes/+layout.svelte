<script lang="ts">
	import '../app.css';
	import '@fontsource/anton';
	import '@fontsource-variable/rubik';
	import '@fontsource-variable/jetbrains-mono';

	import favicon from '$lib/images/ground-up-logo.svg';
	import { onMount } from 'svelte';

	let opacity: number = 0;

	onMount(() => {
		setTimeout(() => {
			opacity = 1;
		}, 2000);
	});
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<!-- BASE LAYOUT -->
<div id="root" class="root" style={`opacity: ${opacity}; transition: opacity 250ms ease-in;`}>
	<slot />
</div>

<style>
	.root {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;
	}
</style>
