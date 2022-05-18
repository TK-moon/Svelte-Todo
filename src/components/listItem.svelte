<script>
	import { afterUpdate, beforeUpdate, onDestroy, onMount } from "svelte";

	export let index;
	export let title;
	export let completed;
	export let completedTask;
	export let deleteTask;

	onMount(() => {
		console.log("MOUNT");
	})
	beforeUpdate(() => {
		console.log("BEFORE UPDATE");
	})
	afterUpdate(() => {
		console.log("AFTER UPDATE");
	})
	onDestroy(() => {
		console.log("DESTROY");
	})
</script>

<li class="item" class:done={completed}>
	<div class="item-completed">
		<input id={`check-${index}`} type="checkbox" bind:checked={completed} on:change={() => completedTask(index, completed)}>
		<label for={`check-${index}`}></label>
	</div>
	<div class="item-title" class:strikethrough={completed}>{title}</div>
	<div class="item-delete" on:click={() => deleteTask(index)}></div>
</li>

<style lang="scss">
	.item {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		margin-bottom: 15px;
		padding: 7px;
		list-style: none;
		background-color: #fff;
		border-radius: 30px;
		box-shadow: 0 3px 10px 0 #ccc;
		font-weight: 200;
		transition: background-color .1s ease-in-out 0s;
		.item-completed {
			margin-right: 10px;
			input[type=checkbox] {
				display: none;
			}
			input[type=checkbox] + label {
				position: relative;
				width: 25px;
				height: 25px;
				border-radius: 100%;
				background-color: #fff;
				box-shadow: 0 3px 10px 0 #ccc;
			}
			input[type=checkbox]:checked + label {
				box-shadow: 0 3px 10px 0 #bbb inset;
				background-color: #ccc;
				&:before, &:after {
					position: absolute;
					content: "";
					background-color: #444;
				}
				&:before {
					width: 1px;
					height: 6px;
					left: 8px;
					bottom: 6px;
					transform: rotate(-40deg);
				}
				&:after {
					width: 1px;
					height: 13px;
					right: 10px;
					bottom: 5px;
					transform: rotate(40deg);
				}
			}
		}
		.item-title {
			flex: 1;
		}
		.item-delete {
			position: relative;
			margin-left: 10px;
			width: 25px;
			height: 25px;
			border-radius: 100%;
			background-color: #fff;
			box-shadow: 0 3px 10px 0 #ccc;
			display: flex;
			justify-content: center;
			align-items: center;
			&:before, &:after {
				position: absolute;
				content: "";
				width: 1px;
				height: 40%;
				background-color: #888;
				border-radius: 2px;
			}
			&:before {
				transform: rotate(45deg);
			}
			&:after {
				transform: rotate(-45deg);
			}
			&:active {
				box-shadow: 0 3px 10px 0 #ccc inset;
			}
		}
	}
	.done {
		color: #999;
		background-color: rgb(226, 226, 226);
	}
	.strikethrough {
		text-decoration: line-through;
	}
</style>