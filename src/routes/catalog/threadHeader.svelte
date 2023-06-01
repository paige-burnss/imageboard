<script lang="ts">
    export let index: number;
    
    import Icon from "svelte-awesome";
    /// *** Embedded Icons ***
    import bookmark from 'svelte-awesome/icons/bookmark';
    import ellipsisH from 'svelte-awesome/icons/ellipsisH';
  </script>
  
  <div class="flex flex-row align-middle space-x-2 px-4 py-2">
    <span class="badge variant-filled">Board</span>
    <span class="self-center grow">12:34</span>
    <div class="space-x-1">
      <button type="button" class="btn-icon btn-icon-sm variant-ghost">
        <Icon href="/" data={bookmark}/>
      </button>
      <button type="button" class="btn-icon btn-icon-sm variant-ghost">
        <Icon href="/" data={ellipsisH}/>
      </button>
    </div>
  </div>