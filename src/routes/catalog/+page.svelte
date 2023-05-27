<script lang="ts">
    //import VirtualList from 'svelte-tiny-virtual-list';
    //import InfiniteLoading from 'svelte-infinite-loading';
    import { MasonryInfiniteGrid } from "@egjs/svelte-infinitegrid";
	import SearchBar from "./SearchBar.svelte";

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

<div class="container">
  <div class="overlay">
<h1> Browse through the threads</h1>

<nav> <a href="/"> Home </a> 
    <a href="/"> Individual board </a>

    


</nav>

</div>
<div class="flex flex-wrap">
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
  {#each visibleItems as item (item.key)}
    <div class="item">
      <div class="block card card-hover">
        <img class="rounded-t-2xl"
          src={`https://naver.github.io/egjs-infinitegrid/assets/image/${
            (item.key % 33) + 1
          }.jpg`}
          alt="egjs"
        />
        <div class="p-2 flex flex-nowrap">
          <div><span class="badge variant-filled">Badge</span></div>
          <div>02</div>
          <div>03</div>
        </div>
        <div class="p-4">
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
          </p>
        </div>
      </div>
    </div>
  {/each}
</MasonryInfiniteGrid>

</div>
</div>







  
