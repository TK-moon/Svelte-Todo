<script>
	export let today;
</script>

<div id="date">
	<h1>{today.format('dddd')}</h1>
	<h2>{today.format('Do')}</h2>
	<p>{today.format('MMMM')}</p>
</div>


<style lang="scss">
	#date {
		h1, h2 {
			letter-spacing: 1px;
			display: inline-block;
			margin: 0;
			margin-bottom: 5px;
		}
		h1 {
			font-size: 28px;
			color: #333;
			margin-right: 5px;
			font-weight: 600;
		}
		h2 {
			color:rgb(138, 138, 138);
			font-weight: 200;
		}
		p {
			color:rgb(138, 138, 138);
			font-weight: 300;
		}
	}
</style>