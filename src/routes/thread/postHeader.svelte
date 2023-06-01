<script lang="ts">
  export let index: number;
  
  import Icon from "svelte-awesome";
  /// *** Embedded Icons ***
  import reply from 'svelte-awesome/icons/reply';
  import bookmark from 'svelte-awesome/icons/bookmark';
  import ellipsisH from 'svelte-awesome/icons/ellipsisH';
</script>


<div class="flex flex-row align-middle space-x-2 px-2">
  {#if index == 0}
    <span class="badge variant-filled">Board</span>
  {/if}
  <span class="badge variant-filled">@{10*2}#{4}</span>
  <span class="grow">n minutes ago</span>
  <div class = space-x-4>
    <Icon href="/" data={reply}/>
    {#if index == 0}
      <Icon href="/" data={bookmark}/>
    {/if}
    <Icon href="/" data={ellipsisH}/>
  </div>
</div>