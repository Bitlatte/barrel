<script lang="ts">
	import BoolModeler from './bool-modeler.svelte';
	import ObjectModeler from './object-modeler.svelte';
	import StringModeler from './string-modeler.svelte';
	import Nested from './nested.svelte';
	let array: any[] = [''];
	let options: any[] = ['string'];
</script>

<div class={'my-3'}>
	{#each array as value, index}
		<div class={`flex my-3 justify-start items-center gap-5`}>
			<div class={'input-group w-auto'}>
				<span>Type</span>
				<select class={'select focus:outline-none'} bind:value={options[index]}>
					<option>string</option>
					<option>number</option>
					<option>boolean</option>
					<option>map</option>
					<option>array</option>
					<option>null</option>
				</select>
			</div>
			{#if options[index] === 'string' || options[index] === 'number'}
				<StringModeler />
			{/if}
			{#if options[index] === 'boolean'}
				<BoolModeler />
			{/if}
			{#if options[index] === 'null'}
				<div />
			{/if}
		</div>
		{#if options[index] === 'map'}
			<Nested>
				<ObjectModeler />
			</Nested>
		{/if}
		{#if options[index] === 'array'}
			<Nested>
				<self:array />
			</Nested>
		{/if}
	{/each}
	<button
		on:click={() => {
			array = [...array, ''];
			options = [...options, 'string'];
		}}
		class={'btn btn-sm capitalize'}>Add Value</button
	>
</div>
