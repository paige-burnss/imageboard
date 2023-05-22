<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-crimson.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/all.css';
	// Most of your app wide CSS should be put in this file
	import '../../app.postcss';


	import { AppShell } from '@skeletonlabs/skeleton';
    import { InputChip } from '@skeletonlabs/skeleton';

	let list = [];

	import { autoModeWatcher } from '@skeletonlabs/skeleton';
	import { LightSwitch } from '@skeletonlabs/skeleton';
	import { SlideToggle, FileButton, AppBar} from '@skeletonlabs/skeleton';

	let value: boolean = false;

	import src from "../images/IMOSHI.png";
</script>

<AppShell>

	<svelte:fragment slot="sidebarLeft">
	<div class="container-sidebar">
		<div class="card">
                    <section class="p-4">
                        <h5 class="h5 font-bold">Boards <button type="button" class="btn-icon btn-sm variant-ringed">+</button> </h5>
                        <div class="input-chip textarea cursor-pointer p-2 rounded-container-token text-token">
                            <div class="h-0 overflow-hidden">
                                <select name="chips-example" multiple="" tabindex="-1">
                                    <option value="foo">foo</option>
                                    <option value="bar">bar</option>
                                    <option value="fizz">fizz</option>
                                    <option value="buzz">buzz</option>
                                </select>
                            </div> 
                            <div class="input-chip-interface space-y-4">
                                <form>
                                    <input type="text" placeholder="Search for boards..." class="input-chip-field unstyled bg-transparent border-0 !ring-0 p-0 w-full">
                                </form> 
                                <div class="input-chip-list flex flex-wrap gap-2">
                                    <div>
                                        <button type="button" class="chip variant-filled">
                                            <span>foo</span><span>✕</span>
                                        </button> 
                                    </div>
                                    <div>
                                        <button type="button" class="chip variant-filled">
                                            <span>bar</span> <span>✕</span>
                                        </button> 
                                    </div>
                                    <div>
                                        <button type="button" class="chip variant-filled">
                                            <span>fizz</span> <span>✕</span>
                                        </button> 
                                    </div>
                                    <div>
                                        <button type="button" class="chip variant-filled">
                                            <span>buzz</span> <span>✕</span>
                                        </button> 
                                    </div>
                                </div>
                            </div>
                    </section>
                    <hr>
                    <section class="p-4">
                    <div class="flex-auto flex justify-between items-center">
                        <h5 class="h5 font-bold">Saved Threads</h5>
                        <small><button type="button" class="btn-icon btn-sm variant-ringed">^</button></small>
					</div>
                    </section>
                </div>
	</div>
	</svelte:fragment>
	<slot />
</AppShell>

<InputChip bind:value={list} name="chips" placeholder="Enter any value..." />