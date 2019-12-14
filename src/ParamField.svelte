<script>
  export let name;
  export let rangeStart;
  export let rangeEnd;
  export let unit;
  export let value;

  $: color =
    value >= rangeStart && value <= rangeEnd ? "black-text" : "red-text";
  $: text = `${name} [${unit}]: ${value}`;
</script>

<h6 class={color}>{text}</h6>
