<script lang="ts">
    export let index;
</script>
{#if index == 0}
  <div class="grid grid-cols-2 gap-4 container">
    <img class="col-span-full rounded-2xl object-cover"
      src={`https://naver.github.io/egjs-infinitegrid/assets/image/1.jpg`}
      alt="egjs"
    />
  </div>
{:else}
  {#if index % 3 > 0}
    <article class="image-post">
      a
    </article>
  {:else}
    <article class="text-post">
      s
    </article>
  {/if}
{/if}