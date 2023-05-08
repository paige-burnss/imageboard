<script>
    import VirtualList from 'svelte-tiny-virtual-list';
    import InfiniteLoading from 'svelte-infinite-loading';
  
    let data = [{
        board: "History",
        replies: 15,
        image: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Attributed_to_Jacob_Hoefnagel_-_Gustavus_Adolphus%2C_King_of_Sweden_1611-1632_-_Google_Art_Project.jpg/1200px-Attributed_to_Jacob_Hoefnagel_-_Gustavus_Adolphus%2C_King_of_Sweden_1611-1632_-_Google_Art_Project.jpg",
        text: "The Catholic Germans deserved the reformation war."
    }];
  
    function infiniteHandler({ detail: { complete, error } }) {
        try {
            // Normally you'd make an http request here...
    
            const newData = [{
                board: "Technology",
                replies: 12,
                image: "https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/60f0d74e-6334-4486-bfe1-216a182188d0/df7awia-916bc0b7-4b6d-46db-8ac7-9dc240f08bcd.png/v1/fill/w_1057,h_756,q_70,strp/peepo_happy_by_korunecka_df7awia-pre.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9OTE1IiwicGF0aCI6IlwvZlwvNjBmMGQ3NGUtNjMzNC00NDg2LWJmZTEtMjE2YTE4MjE4OGQwXC9kZjdhd2lhLTkxNmJjMGI3LTRiNmQtNDZkYi04YWM3LTlkYzI0MGYwOGJjZC5wbmciLCJ3aWR0aCI6Ijw9MTI4MCJ9XV0sImF1ZCI6WyJ1cm46c2VydmljZTppbWFnZS5vcGVyYXRpb25zIl19.Hma94SuVs6T4TItzUKS7q2MGv1FtPw2ZCu9EGWca_8E",
                text: "Richard Stallman is an idiot."
            }];
            
            data = [...data, ...newData];
            complete();
        } catch (e) {
            error();
        }
    }
  </script>
  
  <VirtualList
      width="100%"
      height="100%"
      itemCount={data.length}
      itemSize={768}> <!--TODO: Set item size according to thread image size.-->
    <div slot="item" let:index let:style {style}>
        <div class="h-56 grid grid-cols-2 gap-4 content-start" id="scroll-virtual-custom">
            <div class="justify-self-start">
                <span class="badge variant-filled">{data[index].board}</span>
            </div>
            <div class="justify-self-end">{data[index].replies} replies</div>
            <div class="col-span-full">
                <img class="rounded-lg object-cover" style="width:100%;max-height:512px"
                 src={data[index].image} alt="Placeholder">
            </div>
            <div class="col-span-full">
                {data[index].text}
            </div>
        </div>
    </div>
  
    <div slot="footer">
        <InfiniteLoading on:infinite={infiniteHandler} />
    </div>
  </VirtualList>