<script lang="ts">
    import { MasonryInfiniteGrid } from "@egjs/svelte-infinitegrid";
    import Post from "./post.svelte";
	import { page } from "$app/stores";// FIXME: Not used?

let items = getItems(0, 10);

/*This is a function that returns items for the masonry grid, as described in the comments in "../catalog/+page.svelte"
Could be refactored so that the code is reused rather than repeated.*/
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
  /*This style rule makes each item as wide as the container it is in.
  This effectively turns the "masonry grid" into a normal non-grid list.
  This eliminates the need for a separate library for a normal list.*/
  .item {
    width: 100%;
  }
</style>

  

<!--This is another masonry grid, as described in the comments in "../catalog/+page.svelte"-->
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
      <Post index={item.key} /><!--A component defined in ./post.svelte-->
    </div>
  {/each}
</MasonryInfiniteGrid>
