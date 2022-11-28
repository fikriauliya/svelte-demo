<script>
  let num1 = 0;
  let num2 = 0;
  let num3 = 0;
  $: result1 = parseInt(num1) + parseInt(num2);
  $: result2 = parseInt(result1) + parseInt(num3);
</script>

<h1>Calculator</h1>
<input bind:value={num1} type="text" placeholder="0" style="width:40px" />
+
<input bind:value={num2} type="text" placeholder="0" style="width:40px" />
=
<input value={result1} type="text" placeholder="0" style="width:40px" />
+
<input bind:value={num3} type="text" placeholder="0" style="width:40px" />
=
<input value={result2} type="text" placeholder="0" style="width:40px" />
