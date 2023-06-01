<script lang="ts">
  export let index: number;
  import PostHeader from "./postHeader.svelte";

  import image from "../images/1.jpg";
</script>

{#if index == 0}
  <article class="original-post space-y-4">
    <img class="rounded-2xl object-cover"
      src="{image}"
      alt="egjs"
    />
    <PostHeader index={0} />
    <p>Lorem ipsum bla bla bla</p>
  </article>
{:else}
  {#if index % 3 > 0}
    <article class="image-post space-y-4">
      <PostHeader index={index} />
      <div class="flex flex-row gap-8">
        <img class="rounded-2xl object-cover w-64"
          src="{image}"
          alt="egjs"
        />
        <p>Look at this photograph.</p>
      </div>
    </article>
  {:else}
    <article class="text-post space-y-4">
      <PostHeader index={index} />
      <p>Lorem ipsum bla bla bla</p>
    </article>
  {/if}
{/if}

<hr class="!border-t-2 py-2" />