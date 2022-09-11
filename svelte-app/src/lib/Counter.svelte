<script lang="ts">
  import { greet } from "lib";

  let count: number = 0
  const increment = () => {
    count += 1
  }
</script>

<button on:click={increment} on:click={greet}>
  count is {count}
</button>
