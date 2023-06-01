<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-crimson.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/all.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import './theme.postcss';


	import { AppShell } from '@skeletonlabs/skeleton';
    import { InputChip } from '@skeletonlabs/skeleton';

	let list = [];

	import { autoModeWatcher } from '@skeletonlabs/skeleton';
	import { LightSwitch } from '@skeletonlabs/skeleton';
	import { SlideToggle, FileButton, AppBar} from '@skeletonlabs/skeleton';

	let value: boolean = false;

	import logo from "./images/IMOSHI.png";
</script>

<AppShell>

	<svelte:fragment slot="header">
		<div class="flex-auto flex justify-between items-center header">
			<div>
				<nav> <a href="/"> <img src="{logo}" alt="image" width="50px"/> </a></nav>
			</div>
			<div>
				<AppBar class="!bg-transparent">
				<div class="flex flex-row-reverse items-center gap-4">
					<LightSwitch></LightSwitch>
					<button type="button" class="btn variant-filled">EN</button>
					<!-- <FileButton class="py-4" name="files" button="variant-soft-primary">Language</FileButton> -->
				</div>
				</AppBar>
			</div>
		</div>
	</svelte:fragment>
    <slot />
</AppShell>
