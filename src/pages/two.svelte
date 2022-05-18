<script>
	let a = 0;
	let b = 0;
	
	$: sum = a + b;

	const pow = (a1, b1) => {
		return Math.pow(a1, b1);
	}
</script>

<input type="number" bind:value={a}>
<input type="number" bind:value={b}>
<p>{a} + {b} = {a + b}</p>
<p>$: sum = {sum}</p>
<p>POW: {pow(a, b)}</p>