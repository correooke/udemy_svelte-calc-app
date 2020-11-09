<script>
	import Functions from './components/Functions.svelte';
	import MathOperations from './components/MathOperations.svelte';
	import Numbers from './components/Numbers.svelte';
	import Result from './components/Result.svelte';
	import words from 'lodash.words'

	let stack = ""; 
	$: items = words(stack, /[^-^+^*^/]+/g)
	$: value = items.length > 0 ? items[items.length-1] : "0"

	$: {
		console.log(`value: ${value}`)
	}
	function contentclear() {
		console.log("clear");
		stack = ""
	}

	function deleteKey() {
		// console.log("delete");
		if (stack.length > 0) {
			const newStack = stack.substring(0, stack.length - 1)
			stack = newStack
		}		
	}	

	function clickOperation({detail}) {
		const operation = detail;
		stack = `${stack}${operation}`
	}	

	function clickEqual() {
		// console.log("clickEqual");
		stack = eval(stack).toString()
	}		

	function clickNumber({ detail }) {
		const number = detail;
		// console.log("clickNumber" + number);
		

		stack = `${stack}${number}`
	}			
</script>

<main class={'calculator'}>
	<Result value={value} />
	<Numbers on:clickNumber={clickNumber} />
	<Functions on:contentclear={contentclear} on:delete={deleteKey} />
	<MathOperations on:clickOperation={clickOperation} on:clickEqual={clickEqual} />
	
</main>

<style>
	.calculator {
		position: relative;
		margin: 0 auto;
		width: 320px;
		background-color: #292f36;  
		box-shadow: 0 19px 38px rgba(19, 19, 19, .24),
		0 15px 12px rgba(19, 19, 19, .12);
	}	

</style>
