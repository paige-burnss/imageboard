<script lang="ts">
  export let index: number;
  
  import Icon from "svelte-awesome";
  /// *** Embedded Icons ***
  import reply from 'svelte-awesome/icons/reply';
  import bookmark from 'svelte-awesome/icons/bookmark';
  import ellipsisH from 'svelte-awesome/icons/ellipsisH';
</script>

<!--A row of badges buttons for each post. Buttons currently lack logic.-->
<div class="flex flex-row align-middle space-x-2">
  {#if index == 0}
    <span class="badge variant-filled">Board</span>
  {/if}
  <span class="badge variant-filled">@{10*2}#{4}</span>
  <span class="grow">n minutes ago</span>
  <div class = space-x-4>
    <Icon href="/" data={reply}/>
    {#if index == 0}<!--Only show the bookmark icon for the original post. The original post has an index of 0.-->
      <Icon href="/" data={bookmark}/>
    {/if}
    <Icon href="/" data={ellipsisH}/>
  </div>
</div>