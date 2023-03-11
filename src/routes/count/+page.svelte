<script>
	import { count } from './store';
	let countValue;

	count.subscribe((value) => {
		countValue = value;
	});
</script>

<h1>{countValue}</h1>
