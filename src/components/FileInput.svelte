<script>
  import { uuid } from "../utils/message";
  export let label = "",
    input = "",
    className;
  export { className as class };

  const uid = uuid("LABEL");

  const uniqueLabel = label || uid.create();
</script>

<div class={className + " cursor-pointer"}>
  <label
    class="flex items-center justify-center cursor-pointer"
    for={uniqueLabel}
  >
    <span class="inline-block">
      <slot />
    </span>
    <slot name="icon" />
  </label>
  <input
    {...$$restProps}
    bind:this={input}
    on:change
    on:input
    type="file"
    hidden
    id={uniqueLabel}
  />
</div>
