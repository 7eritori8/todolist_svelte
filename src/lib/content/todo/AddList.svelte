<script>
	import { todoStore } from '../../module/todo/todoStore';
	function onSubmit() {
		if (text === '') {
			return;
		}
		todoStore.update((n) => {
			n.push(text);
			text = '';
			return n;
		});
	}
	let todoArray;

	todoStore.subscribe((value) => {
		todoArray = value;
	});
	let text = '';
</script>

<!--
  This example requires some changes to your config:
  
  ```
  // tailwind.config.js
  module.exports = {
    // ...
    plugins: [
      // ...
      require('@tailwindcss/forms'),
    ],
  }
  ```
-->
<div class="bg-white shadow sm:rounded-lg">
	<div class="px-4 py-5 sm:p-6">
		<h3 class="text-base font-semibold leading-6 text-gray-900">Todoを追加</h3>
		<!-- <div class="mt-2 max-w-xl text-sm text-gray-500">
			<p>Todo</p>
		</div> -->
		<form class="mt-5 sm:flex sm:items-center">
			<div class="w-full sm:max-w-xs">
				<input
					bind:value={text}
					type="text"
					class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
					placeholder="todo"
				/>
			</div>
			<button
				on:click={onSubmit}
				type="submit"
				class="mt-3 inline-flex w-full items-center justify-center rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600 sm:mt-0 sm:ml-3 sm:w-auto"
				>＋</button
			>
		</form>
	</div>
</div>
<!-- <p>{todoArray}</p> -->
