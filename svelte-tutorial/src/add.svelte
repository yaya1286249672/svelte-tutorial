<script>
	let a = 1;
    let b = 2;
    const list = [];
  for (let i = 0; i < 50000; i++) {
    list.push(i);
  }
  let data = list;
    function click(index) {
    return () => {
      data[index] = "test";
    };
  }
</script>

<input type="number" bind:value={a}>
<input type="number" bind:value={b}>
<p>{a} + {b} = {a + b}</p>
{#each data as d, i}
<h1 on:click={click(i)}>
    <span>
      <span>
        <span>
          <span>{i} {d}!</span>
        </span>
      </span>
    </span>
  </h1>
  {/each}