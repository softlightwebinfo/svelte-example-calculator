<button on:click>
  <slot></slot>
</button>

<style lang="scss">
  button {
    border-radius: 200px;
    height: var(--button_size);
    min-width: var(--button_size);
    background-color: var(--button_color);
    transition: all .3s ease-in-out;
    border: 4px solid #d9a2a2;
    color: var(--button_text);
    font-size: var(--font-size);
    width: 100%;
    display: inline-flex;
    align-items: center;
    justify-content: center;

    &:hover {
      --button_color: gray;
      cursor: pointer;
    }
  }
</style>
