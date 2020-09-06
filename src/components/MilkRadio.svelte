<script>
  export let milk;
  export let value;
  export let activeMilk;

  let active;

  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  function setActive() {
    dispatch("message", {
      milk: milk,
      value: value,
    });
  }

  $: if (activeMilk === milk) {
    active = true;
  } else {
    active = false;
  }
</script>

<style>
  button {
    background-color: rgb(255, 255, 255);
    display: block;
    width: 100%;
    text-align: left;
    font-size: 14pt;
  }
  button:hover {
    background-color: rgb(233, 233, 233);
  }
  .active {
    font-weight: bold;
  }
</style>

<button class:active on:click={setActive}> {milk} {value}% </button>
