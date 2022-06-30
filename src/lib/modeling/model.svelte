<script lang="ts">
	import Section from '$lib/section.svelte';
	import Editable from '$lib/modeling/editable.svelte';
	import DocumentModeler from '$lib/modeling/document-modeler.svelte';
</script>

<div class={'mockup-window bg-base-300 shadow-md md:min-w-[750px]'}>
	<div class={'p-4 bg-base-200 overflow-hidden'}>
		<div class={'text-sm breadcrumbs'}>
			<ul>
				<li>
					<div class={'breadcrumbs'}>
						<ul>
							<li>
								<Editable placeholder={'Collection'} />
							</li>
							<li>
								<Editable placeholder={'Document'} uuid />
							</li>
						</ul>
					</div>
				</li>
			</ul>
		</div>
		<div>
			<DocumentModeler />
		</div>
	</div>
</div>
