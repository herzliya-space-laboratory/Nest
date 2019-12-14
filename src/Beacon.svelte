<script>
  import TelemCard from "./TelemCard.svelte";

  const mib = {};
  let data = [
    {
      "Parameter Name": "number_resets",
      "Raw Data": "00-00-00-03",
      Value: "3",
      Unit: "none"
    }
  ];

  $: subSystems = parseData(data, mib);

  function parseData(data, mib) {
    subSystems = [];

    data.forEach(param => {
      const paramInfo = mib[param["Parameter Name"]];

      const rangeStart = paramInfo.rangeStart;
      const rangeEnd = paramInfo.rangeStart;
      const description = paramInfo.description;

      const parse = description.split(",");
      const subSystem = parse[0];
      const name = parse[1];

      const unit = param.Unit;
      const value = param.Value;

      if (!subSystem in subSystems) {
        subSystems.push({
          name: subSystem,
          params: []
        });
      }

      const subSystemIndex = findSubSystemIndex(subSystems, subSystem);
      params[subSystemIndex].params.push({
        name: name,
        unit: unit,
        value: value,
        rangeStart: rangeStart,
        rangeEnd: rangeEnd
      });
    });

    return params;
  }

  function findSubSystemIndex(subSystems, subSystem) {
    for (let i = 0; i < subSystems.length; i++) {
      if (subSystem[i].name === subSystem) return i;
    }

    return null;
  }
</script>

<div class="row">
  {#each subSystems as { name, params }}
    <TelemCard title={name} parameters={params} />
  {/each}
</div>
