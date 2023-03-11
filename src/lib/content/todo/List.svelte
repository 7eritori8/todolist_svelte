<script lang="ts">
	export let todo = '';
	export let onDelete = function (i: number) {};
	export let i = 0;
</script>

<li class="py-4">
	<div class="flex items-center space-x-4">
		<div class="min-w-0 flex-1">
			<p class="truncate text-sm font-medium text-gray-900">{todo}</p>
		</div>
		<div
			on:click={() => {
				onDelete(i);
			}}
		>
			<a
				href="#"
				class="inline-flex items-center rounded-full bg-white px-2.5 py-1 text-xs font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50"
				>完了</a
			>
		</div>
	</div>
</li>
