<script>
	export let value;
	export let placeholder;
</script>

<input id="addInput" type="text" placeholder={placeholder} bind:value={value}>

<style lang="scss">
	#addInput {
		flex: 1;
		margin-right: 20px;
		border-radius: 45px;
		font-weight: 300;
		color: #333;
		outline: none;
		padding: 20px;
		height: 45px;
		border: none;
		box-shadow: 0 3px 10px 0 #ccc;
		background-color: #fff;
		border: 0px solid #fff;
		transition: box-shadow .3s ease-in-out 0s, border .3s ease-in-out 0s;
		&:hover, &:focus {
			box-shadow: 0 3px 20px 0 #999;
		}
	}
</style>