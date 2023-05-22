<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-crimson.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/all.css';
	// Most of your app wide CSS should be put in this file
	import '../../app.postcss';


	import { AppShell } from '@skeletonlabs/skeleton';
    import { InputChip } from '@skeletonlabs/skeleton';

	let list: string[] = ['video games', 'AI', 'techno', 'music'];

	import { autoModeWatcher } from '@skeletonlabs/skeleton';
	import { LightSwitch } from '@skeletonlabs/skeleton';
	import { SlideToggle, FileButton, AppBar} from '@skeletonlabs/skeleton';

	let value: boolean = false;
</script>

<AppShell>

	<svelte:fragment slot="sidebarLeft">
        <div class="container-sidebar flex flex-col space-y-4" id="custom-sidebar-threads">
            <div class="flex space-x-4">
                <h5> Boards  </h5>
                 <button type="button" class="btn-icon btn-icon-sm variant-ringed-surface">+</button> 
            </div>
        <InputChip bind:value={list} name="chips" maxlength={5} class="!bg-transparent" placeholder="Enter any value..." />
        <hr/>
        <div class="flex space-x-8">
            <h5> Saved Threads  </h5>
             <button type="button" class="btn-icon btn-icon-sm variant-soft-surface ">^</button>
        </div>

    </div>
	</svelte:fragment>

	<slot />
</AppShell>
