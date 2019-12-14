<script>
  import ParamField from "./ParamField.svelte";

  export let title;
  export let parameters;
</script>

<div class="col l4 m8 s10">
  <div class="card medium white">
    <div class="card-content black-text">
      <span class="card-title">{title}</span>
      {#each parameters as { name, unit, rangeStart, rangeEnd, value }}
        <ParamField {name} {unit} {rangeStart} {rangeEnd} {value} />
      {/each}
    </div>
  </div>
</div>
