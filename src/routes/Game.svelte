<script lang="ts">
  import SquareGrid from './SquareGrid.svelte';
  import type { Level } from './levels';
  import { levels } from './levels';

  let level = levels[0];
  let grid: string[] = createGrid(level);

  function createGrid(level: Level) {
    const copy = level.emojis.slice();
    let pairs: string[] = [];

    for (let i = 0; i < level.size ** 2 / 2; i += 1) {
      const index = Math.floor(Math.random() * copy.length);
      const emoji = copy[index];

      pairs.push(emoji);
      copy.splice(index, 1);
    }

    pairs.push(...pairs);

    return pairs;
  }
</script>

<div class="ematchi h-full grid content-center justify-center">
  <div class="countdown w-[80em] h-[10em] bg-slate-400" />
  <SquareGrid {grid} />
  <div class="result w-[80em] h-[10em] bg-slate-400" />
</div>

<style lang="scss">
  .ematchi {
    font-size: min(1vmin, 0.3rem);
  }
</style>
