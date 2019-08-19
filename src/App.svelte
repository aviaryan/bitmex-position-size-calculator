<script>
	let balance = 1;
	let risk = 5;
	let sl = 15;

	let tradeBal;
	$: tradeBal = balance * (risk / sl);
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
		<input type="number" placeholder="5" value="5" bind:value={risk} />
	</div>
	<div>
		SL percentage
		<input type="number" placeholder="15" value="15" bind:value={sl} />
	</div>
	<div>You should trade with {tradeBal.toFixed(4)} btc.</div>
</div>
