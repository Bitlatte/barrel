<script lang="ts">
	export let alt: boolean = false;
	export let large: boolean = false;
</script>

<div class={`${alt ? 'bg-base-200 ' : ''}flex justify-center items-center py-10`}>
	<div class={`${large ? 'w-full' : 'w-[90%] md:w-3/4'}`}>
		<slot />
	</div>
</div>
