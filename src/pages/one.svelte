<script>
	let agreed = false;
	const click = (e) => {
		agreed = !agreed;
		console.log(agreed);
	}
</script>

<input type="button" value="Button" on:click={click} />

<p>{agreed}</p>

{#if agreed}
	<p>Y</p>
{:else}
	<p>N</p>
{/if}