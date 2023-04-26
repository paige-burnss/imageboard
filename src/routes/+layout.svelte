<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-crimson.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/all.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	// Add App Shell
	import { AppShell } from '@skeletonlabs/skeleton';
	import { ListBox, ListBoxItem } from '@skeletonlabs/skeleton';
	let valueSingle: string = 'books';
</script>

<AppShell>
	<svelte:fragment slot="sidebarLeft">Sidebar Left</svelte:fragment>
	<svelte:fragment slot="sidebarRight">
		<ListBox>
			<ListBoxItem bind:group={valueSingle} name="medium" value="books">Books</ListBoxItem>
			<ListBoxItem bind:group={valueSingle} name="medium" value="movies">Movies</ListBoxItem>
			<ListBoxItem bind:group={valueSingle} name="medium" value="tv">TV</ListBoxItem>
		</ListBox>
	</svelte:fragment>
	<!-- Router Slot -->
	<slot />
	<!-- ---- / ---- -->
</AppShell>
