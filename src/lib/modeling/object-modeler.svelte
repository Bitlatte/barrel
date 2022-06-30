<script lang="ts">
	import ArrayModeler from './array-modeler.svelte';
	import BoolModeler from './bool-modeler.svelte';
	import StringModeler from './string-modeler.svelte';
	import Nested from './nested.svelte';

	let options: any[] = ['string'];
	let fields: any[] = [''];
</script>

<div class={'flex flex-col justify-start items-start gap-3 my-3'}>
	{#each fields as field, index}
		<div class={'flex justify-start items-center gap-2'}>
			<div class={'input-group w-auto'}>
				<span>Field</span>
				<input class={'input focus:outline-none'} />
			</div>
			<span class={'text-xl'}>=</span>
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
				<svelte:self />
			</Nested>
		{/if}
		{#if options[index] === 'array'}
			<Nested>
				<ArrayModeler />
			</Nested>
		{/if}
	{/each}
	<button
		on:click={() => {
			fields = [...fields, ''];
			options = [...options, 'string'];
		}}
		class={'btn btn-sm capitalize'}>Add Field</button
	>
</div>
