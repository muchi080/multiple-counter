<script>
	let i = 1;
	let name = 'new'
	let counter= 0;
	let boxes = [
		{ id: 0, description: '' },
	];
	let uid = boxes.length + 1;
	function addCounter() {
		const box = {
			id: uid++,
			description: ""
		};
			boxes = [box, ...boxes];
	}
	function remove(box) {
		boxes = boxes.filter(t => t !== box);
	}
	function increment() {
		counter=counter + 1;
	}
	function decrement() {
		if (counter>0) {counter=counter - 1;}
	}
	function resett() {
		counter=0;
	}


</script>

<main>
	<h1>Multiple Counter</h1>
	{#each boxes as box (box.id)}
<div class="counter-container">
	<div class="container" id="counter_0">
		<input class="counter-name" value={name}>
		<span class="counter">{counter}</span>
		<button  on:click={increment} class="btn btn-plus">+</button>
		<button on:click={decrement} class="btn btn-minus">-</button>
		<button on:click={resett} class="btn btn-reset">0</button>
		<button on:click="{() => remove(box)}" class="btn btn-delete">x</button>
	</div>
</div>
		{/each}

	<button class="new-counter" on:click={addCounter}>new counter</button>
	<p>title list:{name}</p>
	<p>sum of count: {counter}</p>
</main>


<style>
	main, .new-counter {
		text-align: center;
		
		}

	h1 {
		color: #000000;
		font-size: 4em;
		font-weight: inherit;
		width: 100%;
		display: block;
		padding: 1em;
		margin: 0;
		max-width: 240rem;
		margin-block-start: 0.67em;
    	margin-block-end: 0.67em;
    	margin-inline-start: 0px;
    	margin-inline-end: 0px;
	}
	.btn{
		max-width: 24rem;
		margin:auto ;
		
	}
	.counter{
		margin: 0.5rem 2rem;
	}

	.container, .new-counter {
		background-color: #f7fafc;
		box-shadow: 0 10px 15px -3px rgb(0 0 0 / 10%), 0 4px 6px -2px rgb(0 0 0 / 5%);
		position : relative;
		max-width: 24rem;
		align-items : center;
		display: flex;
		border-radius: 0.25rem;
		max-width: 24rem;
		margin-bottom: 0.5rem;
		margin:auto;

	}
	.counter-name{
		width: 8rem; 
		--text-opacity: 1;
		color: rgba(113,128,150,var(--text-opacity));
		padding-left: 0.25rem;
    	padding-right: 0.25rem;
		margin-left: 1rem;
	    margin-right: 1rem;
		padding: 0;
		line-height: inherit;
		font-family: inherit;
   		font-size: 100%;
		overflow: visible;
		
	}
	.counter{
		/* position: absolute; */
		/* left: 50%; */
   	 	padding: 0rem,16rem;
		font-size: 1.125rem;
		font-weight: 700;
		box-sizing: border-box;
    	border-width: 0;
    	border-style: solid;
    	border-color: #e2e8f0;
	}

	.btn{
		color: #ffffff;
		padding-top: 0.25rem;
    	padding-bottom: 0.25rem;
    	padding-left: 0.75rem;
    	padding-right: 0.75rem;
    	margin-top: 0.25rem;
    	margin-bottom: 0.25rem;
    	font-size: 1.125rem;
	}
	.btn-plus{
		background-color: #f56565;
		

	}
	.btn-minus{
		background-color: #4299e1;

	}.btn-reset{
		background-color: #ecc94b;

	}
	.btn-delete{
		color: #a0aec0;
		box-sizing: border-box;
    	border-width: 0;
    	border-style: solid;
    	border-color: #e2e8f0;
		
	}
	.new-counter{
		color: #f7fafc;
		background-color: #68d391;
		--text-opacity: 1;
		max-width: 24rem;
		margin-bottom: 0.5rem;
		margin:auto;
	}
	p, .new-counter{
		display:block;
	}
	
	
</style>
<!-- ここから試験版 -->
