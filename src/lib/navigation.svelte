<script lang="ts">
	import ThemeSelect from '$lib/theme-select.svelte';
	import DiGithubBadge from 'svelte-icons/di/DiGithubBadge.svelte';
</script>

<div class={'flex justify-between items-center bg-base-200 px-10 py-5'}>
	<ThemeSelect />
	<div class={'flex justify-end items-center gap-5'}>
		<!-- Links Start -->
		<a href={'/'} class={'link link-hover'}>Home</a>
		<a href={'/workspace'} class={'link link-hover'}>Workspace</a>
		<a
			href={'https://github.com/Bitlatte/barrel'}
			target={'_blank'}
			class={'link link-hover w-10 h-10'}
		>
			<DiGithubBadge />
		</a>
		<!-- Links End -->
	</div>
</div>
