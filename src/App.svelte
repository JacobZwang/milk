<script>
  import Columns from "./layout/columns.svelte";
  import Milk1 from "./components/Milk1.svelte";

  let milkone;
  let value1;

  function handleActive(event) {
    milkone = event.detail.milk;
    value1 = event.detail.value;
  }
</script>

<Columns>
  <Milk1 on:message={handleActive} />
</Columns>
{milkone}
