<script lang="ts">
  import Square from './Square.svelte';
  export let grid: string[];
</script>

<div class="square-grid grid grid-rows-4 grid-cols-4 gap-1.5 w-[80em] h-[80em] bg-slate-500">
  {#each grid as emoji}
    <Square {emoji} />
  {/each}
</div>
