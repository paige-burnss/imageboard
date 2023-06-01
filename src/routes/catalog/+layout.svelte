<script lang='ts'>
  // The ordering of these imports is critical to your app working properly
  import '@skeletonlabs/skeleton/themes/theme-crimson.css';
  // If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
  import '@skeletonlabs/skeleton/styles/all.css';
  // Most of your app wide CSS should be put in this file
  import '../../app.postcss';


  import { AppShell, InputChip } from '@skeletonlabs/skeleton';
  import { Autocomplete } from '@skeletonlabs/skeleton';
  import type { AutocompleteOption } from '@skeletonlabs/skeleton';
  let inputChip = '';
  let inputChipList: string[] = ['vanilla', 'chocolate'];
  const flavorAllowlist: string[] = ['neapolitan', 'pineapple', 'peach'];

  let boardInput = '';

  const flavorOptions: AutocompleteOption[] = [
    { label: 'Vanilla', value: 'vanilla', keywords: 'plain, basic', meta: { healthy: false } },
    { label: 'Chocolate', value: 'chocolate', keywords: 'dark, white', meta: { healthy: false } },
    { label: 'Strawberry', value: 'strawberry', keywords: 'fruit', meta: { healthy: true } },
    { label: 'Neapolitan', value: 'neapolitan', keywords: 'mix, strawberry, chocolate, vanilla', meta: { healthy: false } },
    { label: 'Pineapple', value: 'pineapple', keywords: 'fruit', meta: { healthy: true } },
    { label: 'Peach', value: 'peach', keywords: 'fruit', meta: { healthy: true } }
  ];

  function onInputChipSelect(event: any): void {
    boardInput = event.detail.label;
  }

</script>

<!-- <div class="grid grid-cols-3 grid-flow-col auto-cols-max"> -->
  <div class="flex-1 flex flex-wrap grow basis-0 max-width:100%">
<div class="float:left;width:250px">
  <div class="flex">
  <aside class="h-screen sticky top-0">
    <div class="container flex-initial w-80">
      <div class="container-sidebar flex flex-col space-y-4" id="custom-sidebar-threads">
      <div class="flex space-x-4">
        <h5> Boards  </h5>
         <button type="button" class="btn-icon btn-icon-sm variant-ringed-surface">+</button> 
      </div>
      <!-- <SearchBar /> -->
      <hr/>
      <InputChip bind:input={inputChip} bind:value={inputChipList} name="chips" />

      <div class="card w-full max-w-sm max-h-48 p-4 overflow-y-auto">
        <Autocomplete
          bind:input={inputChip}
          options={flavorOptions}
          denylist={inputChipList}
          on:selection={onInputChipSelect}
        />
      </div>
                
      <!-- <FilterTags /> -->
      <hr/>
      <div class="flex space-x-8">
      <h5> Saved Threads  </h5>

    </div>
  </aside>
</div>
</div>
  <slot />


</div>

    
  
