<script>
	import CurrencyChart from "./CurrencyChart.svelte";
	import queryString from "query-string";

	export let name = 'eth';
	export let queryParams;
	$: queryParams = queryString.parse(location.search);
</script>

<main>
	<h1>CoinHawk</h1>
	<p>{queryParams.currency}</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

<CurrencyChart currency={queryParams.currency}></CurrencyChart>