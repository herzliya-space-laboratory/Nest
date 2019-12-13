<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  export let cmdName;
  export let id;

  const onRemove = () => {
    dispatch("removeplaylistcmd", id);
  };
</script>

<li href="#{cmdName}" class="collection-item">
  <div>
    {cmdName}
    <a href="#!" on:click={onRemove} class="secondary-content">
      <i class="material-icons">block</i>
    </a>
  </div>
</li>
