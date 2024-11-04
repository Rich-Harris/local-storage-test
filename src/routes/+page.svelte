<script>
	import { LocalStorage } from '$lib/storage.svelte';

	const box = new LocalStorage('box', {
		color: '#ff3e00',
		dimensions: [100, 100]
	});
</script>

<label>
	<input type="color" bind:value={box.current.color} />
	color
</label>

<label>
	<input type="range" bind:value={box.current.dimensions[0]} min={100} max={500} />
	width
</label>

<label>
	<input type="range" bind:value={box.current.dimensions[1]} min={100} max={500} />
	height
</label>

<hr>

<div
	class="box"
	style:background={box.current.color}
	style:width="{box.current.dimensions[0]}px"
	style:height="{box.current.dimensions[1]}px"
></div>

<style>
	label {
		display: flex;
		align-items: center;
		gap: 0.5em;
	}
</style>
