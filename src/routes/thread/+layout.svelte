<script lang='ts'>
    // The ordering of these imports is critical to your app working properly
    import '@skeletonlabs/skeleton/themes/theme-crimson.css';
    // If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
    import '@skeletonlabs/skeleton/styles/all.css';
    // Most of your app wide CSS should be put in this file
    import '../../app.postcss';
  
  import SearchBar from '../catalog/searchBar.svelte';
  
  </script>
  
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
        <hr/>
        <SearchBar /> 
        <hr/>
        <div class="flex space-x-8">
        <h5> Saved Threads  </h5>
  
      </div>
    </aside>
  </div>
  </div>
    <slot />
  
  
  </div>
    