<script context="module">
	import WidgetSelector from '$lib/WidgetSelector.svelte';
	import type { LoadOutput } from '@sveltejs/kit/types/page';

	export const load = (): LoadOutput => {
		return {
			props: {
				widgets: ['WidgetA', 'WidgetB', 'WidgetC']
			}
		};
	};
</script>

<script>
	export let widgets: string[];
</script>

<h1>Widgets</h1>
{#each widgets as widget, index}
	<div>{index}: <WidgetSelector {widget} /></div>
{/each}
