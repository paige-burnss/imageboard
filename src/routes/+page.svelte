<script>
    import VirtualList from 'svelte-tiny-virtual-list';
    import InfiniteLoading from 'svelte-infinite-loading';
  
    let data = ['A', 'B', 'C', 'D', 'E', 'F', /* ... */];
  
    function infiniteHandler({ detail: { complete, error } }) {
      try {
        // Normally you'd make an http request here...
  
        const newData = ['G', 'H', 'I', 'J', 'K', 'L', /* ... */];
        
        data = [...data, ...newData];
        complete();
      } catch (e) {
        error();
      }
    }
  </script>
  
  <VirtualList
      width="100%"
      height={600}
      itemCount={data.length}
      itemSize={50}>
    <div slot="item" let:index let:style {style}>
      Letter: {data[index]}, Row: #{index}
    </div>
  
    <div slot="footer">
      <InfiniteLoading on:infinite={infiniteHandler} />
    </div>
  </VirtualList>