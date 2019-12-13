<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  export let cmdName;

  const onAddToPlaylist = () => {
    dispatch("addplaylistitem", cmdName);
  };
</script>

<a on:click={onAddToPlaylist} href="#{cmdName}" class="collection-item">
  {cmdName}
</a>
