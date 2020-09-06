<script>
  import Column from "@/layout/column.svelte";
  import MilkRadio from "@/components/MilkRadio.svelte";

  let milk1 = "";

  function handleActive(event) {
    milk1 = event.detail.milk;
    dispatch("message", {
      milk: event.detail.milk,
      value: event.detail.value,
    });
  }
</script>

<Column>
  <MilkRadio
    milk={'Heavy Whipping Cream'}
    value={36}
    activeMilk={milk1}
    on:message={handleActive} />
  <MilkRadio
    milk={'Whipping Cream'}
    value={30}
    activeMilk={milk1}
    on:message={handleActive} />
  <MilkRadio
    milk={'Half and Half'}
    value={15}
    activeMilk={milk1}
    on:message={handleActive} />
  <MilkRadio
    milk={'Whole Milk'}
    value={3.5}
    activeMilk={milk1}
    on:message={handleActive} />
  <MilkRadio
    milk={'Low Fat'}
    value={1}
    activeMilk={milk1}
    on:message={handleActive} />
  <MilkRadio
    milk={'Nonfat / Skim Milk'}
    value={0}
    activeMilk={milk1}
    on:message={handleActive} />
</Column>
{milk1}
