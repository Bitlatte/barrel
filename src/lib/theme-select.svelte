<script lang="ts">
	const options = [
		{ name: 'Light', value: 'light' },
		{ name: 'Dark', value: 'dark' },
		{ name: 'Lofi', value: 'lofi' },
		{ name: 'Black', value: 'black' },
		{ name: 'Synthwave', value: 'synthwave' }
	];
</script>

<select data-choose-theme class={'select select-bordered select-sm'}>
	<option disabled selected>Choose a theme</option>
	{#each options as option}
		<option value={option.value}>{option.name}</option>
	{/each}
</select>
