<script>
  import CommandTable from "./CommandTable.svelte";
  export let name;
</script>

<main>
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css" />
  <script
    src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js">

  </script>
  <div class="card-panel teal lighten-2">
    This is a card panel with a teal lighten-2 class
  </div>

  <h1 class="green-text">Hello {name}!</h1>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>

  <CommandTable />
</main>
