<script lang="ts">

import { AppBar } from '@skeletonlabs/skeleton';
import { SlideToggle } from '@skeletonlabs/skeleton';

let value: boolean = false;

</script>

<AppBar>
    <svelte:fragment slot="trail"><SlideToggle name="slider-label" checked> <icon> dark mode</icon></SlideToggle> 
</svelte:fragment>
</AppBar>

<!-- <nav> <a href="/"> Home </a> 
    <a href="/boards"> Popular boards</a>

</nav> -->

  
<div class="container mx-auto justify-content-center align-items-center">

    <h1 class="text-center"> IMOSHI </h1>

    
</div>



<div class="container mx-auto">


</div>


<div class="container mx-auto">

    <nav> <a href="/threads"> Popular Threads </a></nav>

</div>

