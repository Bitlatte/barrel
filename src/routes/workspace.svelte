<script lang="ts">
	import { mode } from '$app/env';

	import Model from '$lib/modeling/model.svelte';
	import Section from '$lib/section.svelte';
	import FaPlus from 'svelte-icons/fa/FaPlus.svelte';
	import FaTimes from 'svelte-icons/fa/FaTimes.svelte';
	import { onMount } from 'svelte/internal';

	const dec2hex = (dec: any) => {
		return dec.toString(16).padStart(2, '0');
	};

	const genUUID = () => {
		const arr = new Uint8Array(20 / 2);
		window.crypto.getRandomValues(arr);
		return Array.from(arr, dec2hex).join('');
	};

	const addModel = () => {
		models = [...models, { id: genUUID(), component: Model }];
	};
	$: console.log(models);

	let models: any[] = [];

	onMount(() => {
		models = [...models, { id: genUUID(), component: Model }];
	});
</script>

<Section large>
	<div class={'flex flex-col justify-center items-center gap-10'}>
		{#each models as model (model.id)}
			<div class={'indicator'}>
				<span class={'indicator-item'}>
					<button
						class={'btn btn-circle btn-primary btn-sm'}
						on:click={() => {
							models = models.filter((item) => item.id !== model.id);
						}}
					>
						<div class={'w-4 h-4'}><FaTimes /></div>
					</button>
				</span>
				<svelte:component this={model.component} />
			</div>
		{/each}
		<button class={'btn btn-circle capitalize shadow-sm'} on:click={addModel}>
			<div class={'w-5 h-5'}>
				<FaPlus />
			</div>
		</button>
	</div>
</Section>
