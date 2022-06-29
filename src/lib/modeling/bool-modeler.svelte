<script lang="ts">
	let selected: string;
	let options: string[] = ['true', 'false'];
</script>

<div class={'input-group w-auto'}>
	<span>Value</span>
	<select class={'select focus:outline-none'} bind:value={selected}>
		{#each options as option}
			<option>{option}</option>
		{/each}
	</select>
</div>
