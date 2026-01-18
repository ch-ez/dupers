<script>
	import { onMount } from 'svelte';

	onMount(async () => {
		const Particles = (await import('$lib/particles-js.js')).default;
		Particles.init({
			selector: '.particles-js-canvas-el'
		});
	});
</script>


<div id="particles-js">
	<canvas class="particles-js-canvas-el"></canvas>
</div>

<style>
    .particles-js-canvas-el {
        z-index: -1000;
        position: absolute;
        display: block;
        top: 0;
        left: 0;
    }

</style>