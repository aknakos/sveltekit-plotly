<script>
	import Plotly from '../lib/Plotly.svelte';
</script>

<Plotly
	data={[{ x: [0, 1, 2], y: [0, 1, 2] }]}
	on:click={(e) => console.log(e)}
	on:selected={(e) => console.log(e)}
	on:relayout={(e) => console.log('relayout', e)}
/>
