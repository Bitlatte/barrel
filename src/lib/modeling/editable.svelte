<script lang="ts">
	import { tick } from 'svelte/internal';
	export let placeholder: string;
	let text: string = '';
	let value: string;
	export let uuid: boolean = false;

	let input: any;

	const dec2hex = (dec: any) => {
		return dec.toString(16).padStart(2, '0');
	};

	const genUUID = () => {
		const arr = new Uint8Array(20 / 2);
		window.crypto.getRandomValues(arr);
		return Array.from(arr, dec2hex).join('');
	};
</script>

{#if text !== ''}
	<p
		class={'btn btn-ghost btn-sm capitalize underline'}
		on:click={(e) => {
			value = text;
			text = '';
			tick().then(() => input.focus());
		}}
	>
		{text}
	</p>
{:else if uuid}
	<div class={'input-group'}>
		<input
			class={'input input-sm focus:outline-none'}
			bind:value
			bind:this={input}
			{placeholder}
			on:blur={(e) => {
				if (value.length >= 1) {
					text = value;
				}
			}}
		/>
		<button
			class={'btn btn-primary btn-sm'}
			on:click={() => {
				text = genUUID();
			}}>UUID</button
		>
	</div>
{:else}
	<input
		class={'input input-sm focus:outline-none'}
		bind:value
		bind:this={input}
		{placeholder}
		on:blur={(e) => {
			if (value.length >= 1) {
				text = value;
			}
		}}
	/>
{/if}
