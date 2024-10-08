<script>
  let name = '';
  let age = '';

  $: console.log(name)
  $: console.log(age)
</script>

<div class="container">
  <h1>My form:</h1>

  <div class="mb-3">
    <label for="name" class="form-label">Name</label>
    <input type="text" class="form-control" bind:value={name}>
  </div>

  <div class="mb-3">
    <label for="age" class="form-label">Age</label>
    <input type="text" class="form-control" bind:value={age}>
  </div>


</div>