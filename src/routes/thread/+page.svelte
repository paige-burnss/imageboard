<script lang="ts">
    import { MasonryInfiniteGrid } from "@egjs/svelte-infinitegrid";
    import Post from "./post.svelte";

let items = getItems(0, 10);

function getItems(nextGroupKey: number, count: number) {
  const nextItems = [];

  for (let i = 0; i < count; ++i) {
    const nextKey = nextGroupKey * count + i;

    nextItems.push({ groupKey: nextGroupKey, key: nextKey });
  }
  return nextItems;
}
</script>

<style>
  .item {
    width: 100%;
  }
</style>

  
<!-- <h1> Browse through the threads</h1>

<nav>
  <a href="/"> Home </a> 
  <a href="/thread"> Individual board </a>
</nav> -->

<MasonryInfiniteGrid
  class="container divide-y divide-slate-700"
  gap={5}
  {items}
  on:requestAppend={({ detail: e }) => {
    const nextGroupKey = (+e.groupKey || 0) + 1;

    items = [...items, ...getItems(nextGroupKey, 10)];
  }}
  let:visibleItems
>
  {#each visibleItems as item (item.key)}
    <div class="item space-y-4">
      <Post index={item.key} />
    </div>
  {/each}
</MasonryInfiniteGrid>
