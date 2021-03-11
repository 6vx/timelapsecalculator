<script lang="ts">
	import TimeLapseCalculator from './TimeLapseCalculator.svelte';
	import Signature from './Signature.svelte';
	// export let name: string;
</script>

<main>
	<TimeLapseCalculator />
	<Signature />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>