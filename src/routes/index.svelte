<script lang="ts">
	import Heading from '$lib/heading.svelte';
	import SubHeading from '$lib/sub-heading.svelte';
	import Section from '$lib/section.svelte';
	import Model from '../lib/modeling/model.svelte';
</script>

<Section large>
	<div class={'w-full h-full flex flex-col justify-center items-center gap-10'}>
		<Model />
		<div class={'w-2/3 flex justify-end items-center'}>
			<a class={'btn btn-outline btn-sm'} href={'/workspace'}>Open Workspace</a>
		</div>
	</div>
</Section>

<Section alt>
	<Heading>Data Modeling</Heading>
	<SubHeading><span class={'italic ml-5'}>the process of creating a data model</span></SubHeading>
	<div class={'mt-5'}>
		<p>
			This tool was inspired by Firebase. When adding a document to a Firebase Firestore Database,
			they provide a rather beautiful UI to build the document. We wanted to make that into a tool
			for everyone to use. Below we have documented the intended purpose of this tool and what we
			plan on doing with it in the future.
		</p>
	</div>
</Section>

<Section>
	<Heading>Purpose</Heading>
	<div class={'my-5'}>
		<p>
			We found that when trying to create data models it was more often than not easier when you can
			visually see how the data will look. While you could just open a new JSON file and start
			building an example of your data, eventually it will get difficult to read as you get more
			deeply nested into the data structure. When we saw Firebase's Document Editor for the first
			time we fell in love. It was easy to understand, quick to use, and visually stunning. So we
			set out to create our own version of it.
		</p>
	</div>
	<Heading>Into the Future</Heading>
	<div class={'my-5'}>
		<p>
			Eventually we might make this into a free service that you can hook up to any document
			database and create and edit documents right from the browser but for now it is simply a tool
			for you to visually model your data.
		</p>
	</div>
</Section>
