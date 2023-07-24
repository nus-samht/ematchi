<script>
  import Square from './Square.svelte';
  import { levels } from './levels';
</script>

<div class="ematchi h-full grid content-center justify-center">
  <div class="countdown w-[80em] h-[10em] bg-slate-400" />
  <div class="squares grid grid-rows-4 grid-cols-4 gap-1.5 w-[80em] h-[80em] bg-slate-500">
    {#each Array(16) as _}
      <Square />
    {/each}
  </div>
  <div class="result w-[80em] h-[10em] bg-slate-400" />
</div>

<style lang="scss">
  .ematchi {
    font-size: min(1vmin, 0.3rem);
  }
</style>
