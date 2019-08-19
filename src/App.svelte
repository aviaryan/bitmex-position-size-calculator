<script>
	let balance = 1;
	let risk = 5;
	let entry = 12945;
	let sl = 12670;
	let leverage = 10;

	let tradeBal;
	$: {
		const slPercent = ((entry - sl) / entry) * leverage * 100;
		tradeBal = balance * (risk / Math.abs(slPercent));
	}
</script>

<style>
	h1 {
		text-align: center;
	}
	.form {
		margin: 0 auto;
		max-width: 600px;
		width: 100%;
	}
</style>

<h1>Bitmex/Bybit Position Size Calculator</h1>

<div class="form">
	<div>
		Account Balance (in BTC/XBT)
		<input type="number" placeholder="1.00" bind:value={balance} />
	</div>
	<div>
		Percentage to Risk
		<input type="number" placeholder="5" bind:value={risk} />
	</div>
	<div>
		Entry
		<input type="number" placeholder="12945" bind:value={entry} />
	</div>
	<div>
		SL
		<input type="number" placeholder="12670" bind:value={sl} />
	</div>
	<div>
		Leverage (x)
		<input type="number" placeholder="10" bind:value={leverage} />
	</div>
	<div>You should trade with {tradeBal.toFixed(4)} btc.</div>
</div>
