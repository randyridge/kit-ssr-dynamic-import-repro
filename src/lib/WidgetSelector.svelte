<script lang="ts">
	export let widget: string;

	const loadWidget = async (widget: string) => {
		switch (widget) {
			case 'WidgetA':
				return await import('$lib/WidgetA.svelte');
			case 'WidgetB':
				return await import('$lib/WidgetB.svelte');
			case 'WidgetC':
				return await import('$lib/WidgetC.svelte');
		}
	};
</script>

{#await loadWidget(widget) then c}
	<svelte:component this={c.default} />
{:catch error}
	error {error}
{/await}
