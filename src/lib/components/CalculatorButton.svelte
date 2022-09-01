<script lang="ts">
    import Button from "$lib/components/Button.svelte";

    export let label: string;
</script>

<div class="CalculatorButton-{label}">
  <Button on:click>{label}</Button>
</div>
<style lang="scss">
  div {
    &[class *= "0"] {
      grid-column: 1 / span 2;
      grid-row: 5;
    }
  }
</style>
