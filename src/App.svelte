<script>
  let name = '';
  let age = '';
  let terms = true;
  let newsletter;
  let country;

  let formData = {
    name:'',
    age:'',
    terms:true,
    newsletter:'',
    country:''
  }

  // $: console.log(name)
  // $: console.log(age)
  // $: console.log(terms)
  // $: console.log(newsletter)
  // $: console.log(country)

  function validate(){
    if(name !== ''){
      console.log('Valid')
    } else {
      console.log('Not valid')
    }
  }

  function handleSubmit(){
      console.log('Submit form', formData)
  }


</script>

<div class="container">

  <form on:submit|preventDefault={handleSubmit}>
  <h1>My form:</h1>

  <div class="mb-3">
    <label for="name" class="form-label">Name</label>
    <input type="text" class="form-control" bind:value={formData.name}>
  </div>

  <div class="mb-3">
    <label for="age" class="form-label">Age</label>
    <input type="text" class="form-control" bind:value={formData.age}>
  </div>

  <hr/>

  <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" bind:checked={formData.countryterms}>
    <label for="terms" class="form-check-label">Terms</label>
  </div>

  <hr/>

  <h3>Sub to newsletter</h3>
  <div class="form-check">
    <input type="checkbox" class="form-check-input" name="newsletter" value="yes" bind:group={formData.newsletter}> 
    <label for="newsletter" class="form-check-label">YES</label>
  </div>
  <div class="form-check">
    <input type="checkbox" class="form-check-input" name="newsletter" value="no" bind:group={formData.newsletter}> 
    <label for="newsletter" class="form-check-label">NO</label>
  </div>

  <hr/>

  <h3>Country</h3>
  <select class="form-select" bind:value={formData.country}>
    <option disabled selected>Select a country</option>
    <option value="italy">Italy</option>
    <option value="spain">Spain</option>
    <option value="canada">Canada</option>
  </select>

  <button type="submit">submit</button>

</form>
</div>