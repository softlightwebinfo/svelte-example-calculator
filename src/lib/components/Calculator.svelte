<script>
  import CalculatorBox from "$lib/components/CalculatorBox.svelte";
  import CalculatorButton from "$lib/components/CalculatorButton.svelte";

  let buttons = [
    "C", "+/-", "%", "/",
    ...[...new Array(3)].map((_, index) => 7 + index),
    "*",
    ...[...new Array(3)].map((_, index) => 4 + index),
    "-",
    ...[...new Array(3)].map((_, index) => 1 + index),
    "+",
    "0",
    ",",
    "=",
  ];
</script>

<CalculatorBox let:onClick>
  {#each buttons as button,index}
    <CalculatorButton on:click="{onClick(button)}" label={button}/>
  {/each}
</CalculatorBox>
