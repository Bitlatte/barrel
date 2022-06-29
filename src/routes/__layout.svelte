<script lang="ts">
	import '../app.css';
	import Navigation from '../lib/navigation.svelte';
	import { onMount } from 'svelte';
	import { themeChange } from 'theme-change';

	onMount(() => {
		themeChange(false);
	});
</script>

<div>
	<Navigation />
	<div class={'min-h-[90vh]'}>
		<slot />
	</div>
</div>
