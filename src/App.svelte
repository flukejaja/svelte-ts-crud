<script lang="ts">
  let arr = [1];
  const handleAdd = () => {
    arr = [...arr, arr.length + 1];
  };
  const handleDel = (index: number) => {
    arr.splice(index, 1);
    arr = arr;
  };
  const handleEdit = (index: number) => {
    arr[index] = Math.random();
    arr = arr;
  };
</script>

<main>
  <div class="contiainer">
    {#each arr as x, i}
      <div class="item">
        <div>
          <button on:click={() => handleEdit(i)}>{x}</button>
        </div>
        <div><button on:click={() => handleDel(i)}>DEL</button></div>
      </div>
    {/each}
  </div>
  <button on:click={handleAdd}>ADD</button>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    background-color: bisque;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    width: 100%;
  }

  .contiainer {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    grid-gap: 10px;
    justify-items: center;
    align-items: center;
    max-width: 70rem;
    margin: auto;
    width: 100%;
  }
  .item {
    border-radius: 30px;
    border: solid;
    width: 100%;
    height: 240px;
    display: flex;
    gap: 16px;
    justify-content: center;
    align-items: center;
  }
</style>
