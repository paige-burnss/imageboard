<script lang="ts">
  export let index: number;
  
  import Icon from "svelte-awesome";
  /// *** Embedded Icons ***
  import reply from 'svelte-awesome/icons/reply';
  import bookmark from 'svelte-awesome/icons/bookmark';
  import ellipsisH from 'svelte-awesome/icons/ellipsisH';
  import { modalStore } from '@skeletonlabs/skeleton';


  const modal: ModalSettings = {
    type: 'prompt',
    // Data
    title: 'Enter Name',
    body: 'Provide your first name in the field below.',
    // Populates the input value and attributes
    value: 'Skeleton',
    valueAttr: { type: 'text', minlength: 3, maxlength: 10, required: true },
    // Returns the updated response value
    response: (r: string) => console.log('response:', r),
  };
  function replyToPost() {
    modalStore.trigger(modal)
  };
</script>


<div class="flex flex-row align-middle space-x-2">
  {#if index == 0}
    <span class="badge variant-filled">Board</span>
  {/if}
  <span class="badge variant-filled">@{10*2}#{4}</span>
  <span class="grow">n minutes ago</span>
  <div class = space-x-4>
    <button>
      <Icon data={reply} on:click={replyToPost}/>
    </button>
    {#if index == 0}
      <Icon href="/" data={bookmark}/>
    {/if}
    <Icon href="/" data={ellipsisH}/>
  </div>
</div>