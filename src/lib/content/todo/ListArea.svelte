<script lang="ts">
	import List from './List.svelte';
	import { todoStore } from '../../module/todo/todoStore';

	let todoValue: string[] = [];
	todoStore.subscribe((value) => {
		todoValue = value;
	});

	function onDelete(i: number) {
		todoStore.update((n) => {
			n.splice(i, 1);
			return n;
		});
	}
</script>

<div class="px-4 py-5 sm:p-6">
	<div class="mt-6 flow-root">
		<ul role="list" class="-my-5 divide-y divide-gray-200">
			{#each todoValue as todo, i}
				<List {todo} {onDelete} {i} />
			{/each}
		</ul>
	</div>
</div>
