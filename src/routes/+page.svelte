<script lang="ts">
	import { NightVision } from "night-vision";
	import data from "$lib/data-1.json";
	import { onMount } from 'svelte';

	let chart:any

	onMount (() => {
		
		chart.innerHTML = `
		<h1 class="text-5xl mx-auto">Cylex Chart</h1>
		<div id="chart-container"></div>
		`;

		const nchart = new NightVision("chart-container", {
		data,
		autoResize: true,
		colors: { back: "#111113", grid: "#2e2f3055" }
		});


	})

</script>

<div bind:this="{chart}" class="flex flex-col justify-center h-full p-8 gap-8">
</div>
