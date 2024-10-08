<script>
  let name = '';
  let age = '';
  let terms = true;
  let newsletter;

  $: console.log(name)
  $: console.log(age)
  $: console.log(terms)
  $: console.log(newsletter)
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

  <hr/>

  <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" bind:checked={terms}>
    <label for="terms" class="form-check-label">Terms</label>
  </div>

  <hr/>

  <h3>Sub to newsletter</h3>
  <div class="form-check">
    <input type="checkbox" class="form-check-input" name="newsletter" value="yes" bind:group={newsletter}> 
    <label for="newsletter" class="form-check-label">YES</label>
  </div>
  <div class="form-check">
    <input type="checkbox" class="form-check-input" name="newsletter" value="no" bind:group={newsletter}> 
    <label for="newsletter" class="form-check-label">NO</label>
  </div>

</div>