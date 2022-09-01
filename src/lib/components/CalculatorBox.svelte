<script lang="ts">
    export let preview = [];
    let result = 0;

    const update = () => result = eval(preview.join("") || "0");
    export let onClick = (buttonAction) => (ev) => {
        try {
            if (buttonAction == "C") {
                preview.pop();
                preview = preview;
                update()
                return;
            }
            if (buttonAction == "=") {
                preview = [result];
                update()
                return;
            }
            preview = [...preview, buttonAction];
            update()
        } catch (e) {
            console.log(e)
        }
    }
</script>
<div class="CalculatorBox">
  <header>
    <div class="preview">
      {preview.join(" ")}
    </div>
    <div class="result">{result}</div>
  </header>
  <div class="content">
    <slot {onClick}></slot>
  </div>
</div>

<style lang="scss">
  .CalculatorBox {
    background-color: black;
    padding: var(--padding);
    border-radius: 20px;
    box-shadow: 0 0 10px -2px black;
  }

  .content {
    display: inline-grid;
    grid-template-columns: repeat(4, 1fr);
    gap: var(--gap);
  }

  header {
    height: 150px;
    display: flex;
    flex-direction: column;
    text-align: right;
  }

  .preview {
    flex: 1;
    color: white;
  }

  .result {
    font-size: 4em;
    color: white;
  }
</style>
