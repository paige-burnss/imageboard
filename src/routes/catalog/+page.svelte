<script lang="ts">
  //import VirtualList from 'svelte-tiny-virtual-list';
  //import InfiniteLoading from 'svelte-infinite-loading';
  import { MasonryInfiniteGrid } from "@egjs/svelte-infinitegrid";
	import ThreadHeader from "./threadHeader.svelte";

  let items = getItems(0, 10);
  
  //This function returns a list of items to be used in the masonry grid of threads
  function getItems(nextGroupKey: number, count: number) {
  const nextItems = [];
    // Each item must have a unique key for the masonry grid to work.
    // These items should ideally also contain metadata and content for the thread, but that is not implemented yet.
    for (let i = 0; i < count; ++i) {
      const nextKey = nextGroupKey * count + i;

      nextItems.push({ groupKey: nextGroupKey, key: nextKey });
    }
    return nextItems;
  }
</script>


<!--Here we have a component that creates a masonry grid containing all of the active threads. 
The grid is infinite and virtual, meaning that only visible content is rendered(for performance benefits),
and new content is fetched and appended to the bottom of the scrollable grid as the user gets close to the bottom-->
<MasonryInfiniteGrid
  class="container"
  gap={8}
  {items}
  on:requestAppend={({ detail: e }) => {
    const nextGroupKey = (+e.groupKey || 0) + 1;

    items = [...items, ...getItems(nextGroupKey, 10)];
  }}
  let:visibleItems
>
  {#each visibleItems as item (item.key)}<!--Within this "each" block we have the contents of the items in the masonry grid.
  Every item is a card containing an image, a header component, and some text.-->
    <article class="item block card card-hover space-y-1">
      <a href="/thread">
        <img class="rounded-t-2xl"
          src={`https://naver.github.io/egjs-infinitegrid/assets/image/${
            (item.key % 33) + 1
            }.jpg`}
          alt="egjs"
        />
      </a>
      <ThreadHeader index={item.key} /><!--This ThreadHeader is a component defined in threadHeader.svelte
        that makes use of a variable "index" that is equal to the items key-->
      <p class="p-4 pt-0">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
      </p>
    </article>
  {/each}
</MasonryInfiniteGrid> 






  
