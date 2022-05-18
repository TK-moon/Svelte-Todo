<script>
	const array = ['a', 'b', 'c'];
	let checked = [];
</script>

{#each array as item, index (`key-${index}`)}
	<label>
		<input type="checkbox" value={item} bind:group={checked}>
		{item}
	</label>
{/each}
<p>checked : {checked}</p>