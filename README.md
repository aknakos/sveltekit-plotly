# Simple plotly wrapper for svelte

Simple implementation of a wrapper for plotly.js which works with sveltekit.
I made this to easily reuse the logic, but feel free to copy the code in the .svelte file to customize however you want and/or if you don't want to install a dependency only for this.

Usage:

```javascript
<script>
	import Plotly from '../lib/Plotly.svelte';
</script>

<Plotly data={[{ x: [0, 1, 2], y: [0, 1, 2] }]} />
```

Full Example:

```javascript
<script>
	import Plotly from '@aknakos/sveltekit-plotly';
	import { PlotlyLib } from '@aknakos/sveltekit-plotly/store'; //optional

    let reloadPlot = 0; //change this to force reload the plot
    let loaded; // use this to know when the plot is fully loaded

    $: $PlotlyLib.Fx.unhover(??);// use the store's PlotlyLib to use the plotly library as you wish for any custom things

</script>

<div>
    <Plotly
        id='id'
        data={[{x:[1,2,3], y:[2,1,3]}]}
        layout={}
        config={}
        on:hover={...}//unhover event
        on:unhover={...}//hover event
        on:click={...}//click event
        on:selected={...}//selected event
        on:relayout={...}//relayout event
        bind:loaded
        {reloadPlot}
    >
    Loading plotly..
    </Plotly>
</div>
```
