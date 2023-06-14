<script lang="ts">
  export let index: number;// Not used. Only here as a reference for how to pass variables to this component. Will be used in the future.
  
  import  Icon from "svelte-awesome";
  /// *** Embedded Icons ***
  import bookmark from 'svelte-awesome/icons/bookmark';
  import ellipsisH from 'svelte-awesome/icons/ellipsisH';
</script>

<!--Each thread contains this row of badges and buttons. The contents of the badges is hardcoded at the moment, awaiting API integration.
The buttons also lack logic at the moment. WIP-->
<div class="flex flex-row align-middle space-x-2 px-4 py-2">
  <span class="badge variant-filled">Board</span>
  <span class="grow">12:34</span>
  <div class="space-x-4">
    <Icon href="/" data={bookmark}/>
    <Icon href="/" data={ellipsisH}/>
  </div>
</div>