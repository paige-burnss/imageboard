<script lang="ts">
    //import VirtualList from 'svelte-tiny-virtual-list';
    //import InfiniteLoading from 'svelte-infinite-loading';
    import { MasonryInfiniteGrid } from "@egjs/svelte-infinitegrid";

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
    display: inline-block;
    width: 100%;
    max-width: 768px;
    opacity: 1;
  }
</style>

  
<h1> Browse through the threads</h1>

<nav>
  <a href="/"> Home </a> 
  <a href="/thread"> Individual board </a>
</nav>

<MasonryInfiniteGrid
  class="container"
  gap={5}
  {items}
  on:requestAppend={({ detail: e }) => {
    const nextGroupKey = (+e.groupKey || 0) + 1;

    items = [...items, ...getItems(nextGroupKey, 10)];
  }}
  let:visibleItems
>
  <div class="grid grid-cols-2 gap-4 container">
    <img class="col-span-full rounded-2xl object-cover"
      src={`https://naver.github.io/egjs-infinitegrid/assets/image/${
        (0 % 33) + 1
      }.jpg`}
      alt="egjs"
    />
  </div>
  {#each visibleItems as item (item.key)}
    <div class="item">
      {#if item.key % 4 > 1}
        <img class="rounded-t-2xl"
        src={`https://naver.github.io/egjs-infinitegrid/assets/image/${
          (item.key % 33) + 1
        }.jpg`}
        alt="egjs"
        />
      {:else}
      <p>Text</p>
      {/if}
    </div>
  {/each}
</MasonryInfiniteGrid>
