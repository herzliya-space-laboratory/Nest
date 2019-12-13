<script>
  import Command from "./Command.svelte";
  import PlaylistItem from "./PlaylistItem.svelte";

  const mib = ["DummyFunc", "UpdateTime"];
  let playlist = ["DummyFunc"];

  const removePlaylistCmd = e => {
    let x = playlist;
    x.splice(e.detail, 1);
    playlist = x;
  };

  const addPlaylistCmd = e => {
    playlist = [...playlist, e.detail];
  };

  const sendPlaylist = () => {
    //Send the playlist
    playlist = [];
  };
</script>

<main>
  <div class="row">
    <div class="col s6">
      <ul class="collection with-header">
        <li class="collection-header">
          <h4>Commands</h4>
        </li>
        {#each mib as cmdName}
          <Command {cmdName} on:addplaylistitem={addPlaylistCmd} />
        {/each}
      </ul>

    </div>

    <div class="col s6">
      <h4 class="red-text">
        Playlist
        <a
          on:click={sendPlaylist}
          href="#!"
          class="btn-floating btn-large waves-effect waves-light red">
          <i class="material-icons">send</i>
        </a>
      </h4>
      {#if playlist.length === 0}
        <p>
          <i>Empty</i>
        </p>
      {:else}
        <ul class="collection">
          {#each playlist as cmdName, i}
            <PlaylistItem
              {cmdName}
              id={i}
              on:removeplaylistcmd={removePlaylistCmd} />
          {/each}
        </ul>
      {/if}

    </div>
  </div>

</main>
