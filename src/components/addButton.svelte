<script>
	export let onClick;
</script>

<button id="addBtn" on:click={onClick}></button>

<style lang="scss">
	#addBtn {
		width: 45px;
		height: 45px;
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
		border: none;
		border-radius: 50%;
		background-color: #fff;
		box-shadow: 0 3px 10px 0 #ccc;
		transition: box-shadow .3s ease-in-out 0s;
		cursor: pointer;
		&:before, &:after {
			position: absolute;
			content: "";
			width: 2px;
			height: 25%;
			background-color: rgb(138, 138, 138);
			transition: transform .3s ease-in-out 0s;
		}
		&:after {
			transform: rotate(90deg);
		}
		&:hover {
			box-shadow: 0 3px 10px 0 #aaa;
		}
		&:hover:before {
			transform: rotate(180deg);
		}
		&:hover:after {
			transform: rotate(270deg);
		}
		&:active {
			box-shadow: 0 3px 10px 0 #ccc inset;
		}
	}
</style>
