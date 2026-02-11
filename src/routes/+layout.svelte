<script>
	import './layout.css';
	import EmbedStuff from '$lib/components/EmbedStuff.svelte';
	import favicon from '$lib/assets/favicon.png';

	let { children } = $props();
</script>

<EmbedStuff />
<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<div class="bg-gradient"></div>
<div class="bg-grid"></div>
<div class="floating-orbs">
	<div class="orb orb-1"></div>
	<div class="orb orb-2"></div>
	<div class="orb orb-3"></div>
</div>
<!--<Particles/>-->
{@render children()}
