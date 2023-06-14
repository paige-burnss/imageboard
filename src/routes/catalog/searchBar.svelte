<script lang='ts'>
    // The ordering of these imports is critical to your app working properly
    import '@skeletonlabs/skeleton/themes/theme-crimson.css';
    // If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
    import '@skeletonlabs/skeleton/styles/all.css';
    // Most of your app wide CSS should be put in this file
    import '../../app.postcss';
  
  
    import { InputChip } from '@skeletonlabs/skeleton';
    import { Autocomplete } from '@skeletonlabs/skeleton';
    import type { AutocompleteOption } from '@skeletonlabs/skeleton';
    let inputChip = '';
    let inputChipList: string[] = [ ];
    let allowList: string [] = ['videogames, techno, nft, memes, fitness, gardening, memes']; 

  
    const boardCategories: AutocompleteOption[] = [
      { label: 'Videogames', value: 'videogames', keywords: 'gaming, fun', meta: { healthy: false } },
      { label: 'Techno', value: 'techno', keywords: 'music, techno', meta: { healthy: false } },
      { label: 'Gardening', value: 'gardening', keywords: 'hobby', meta: { healthy: true } },
      { label: 'NFT', value: 'nft', keywords: 'hobby, memes, fun, techno', meta: { healthy: false } },
      { label: 'Fitness', value: 'fitness', keywords: 'fitness', meta: { healthy: true } },
      { label: 'Memes', value: 'memes', keywords: 'memes', meta: { healthy: true } }
    ];
  
    function onInputChipSelect(event: any): void {
      inputChip = event.detail.label;
    }
  
  </script>


<InputChip bind:input={inputChip} bind:value={inputChipList} name="chips" />

<div class="card w-full max-w-sm max-h-48 p-4 overflow-y-auto">
  <Autocomplete
    bind:input={inputChip}
    options={boardCategories}
    allowlist={allowList}
    denylist={inputChipList}
    on:selection={onInputChipSelect}
  />
</div>
