<script lang="ts">
  export let index: number;
  import PostHeader from "./postHeader.svelte";

  import image from "../images/1.jpg";
</script>

<!--There are three different kinds of posts.
  Original posts(the post that starts a thread) which always have an image and text,
  Posts with images and text,
  and posts with only text.
  These if else statements are supposed to choose which html to display depending on the type of post,
  but since the items don't yet support any metadata or content,
  we treat posts with an index not divisible by 3 as image+text posts with dummy content.
-->
{#if index == 0}
  <article class="original-post space-y-4 m-4">
    <img class="rounded-2xl object-cover"
      src="{image}"
      alt="egjs"
    />
    <PostHeader index={0} />
    <p>Lorem ipsum bla bla bla</p>
  </article>
{:else}
  {#if index % 3 > 0}<!--In the future this should be something like "if item.hasImage"-->
    <article class="image-post space-y-4 m-4">
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
    <article class="text-post space-y-4 m-4">
      <PostHeader index={index} />
      <p>Lorem ipsum bla bla bla</p>
    </article>
  {/if}
{/if}