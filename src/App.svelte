<script>
  import CommandTable from "./CommandTable.svelte";

  document.addEventListener("DOMContentLoaded", function() {
    var elems = document.querySelectorAll(".dropdown-trigger");
    var instances = M.Dropdown.init(elems, {});
  });
</script>

<main>

  <a class="dropdown-trigger btn" href="#!" data-target="dropdown1">Drop Me!</a>
  <!-- Dropdown Structure -->
  <ul id="dropdown1" class="dropdown-content">
    <li>
      <a href="#!">one</a>
    </li>
    <li>
      <a href="#!">two</a>
    </li>
    <li class="divider" tabindex="-1" />
    <li>
      <a href="#!">three</a>
    </li>
    <li>
      <a href="#!">
        <i class="material-icons">view_module</i>
        four
      </a>
    </li>
    <li>
      <a href="#!">
        <i class="material-icons">cloud</i>
        five
      </a>
    </li>
  </ul>

  <CommandTable />
</main>
