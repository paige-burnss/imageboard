<script lang="ts">
  //import VirtualList from 'svelte-tiny-virtual-list';
  //import InfiniteLoading from 'svelte-infinite-loading';
  import { MasonryInfiniteGrid } from "@egjs/svelte-infinitegrid";
	import ThreadHeader from "./threadHeader.svelte";

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

<!--
<div>
  <h1> Browse through the threads</h1>
  <nav>
    <a href="/"> Home </a> 
    <a href="/"> Individual board </a>
  </nav>
</div>
-->

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
  {#each visibleItems as item (item.key)}
    <article class="item block card card-hover space-y-1">
      <a href="/thread">
        <img class="rounded-t-2xl"
          src={`https://naver.github.io/egjs-infinitegrid/assets/image/${
            (item.key % 33) + 1
            }.jpg`}
          alt="egjs"
        />
      </a>
      <ThreadHeader index={item.key} />
      <p class="p-4 pt-0">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
      </p>
    </article>
  {/each}
</MasonryInfiniteGrid> 






  
