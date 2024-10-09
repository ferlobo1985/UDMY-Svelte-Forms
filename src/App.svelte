<script>
  import { createForm } from "felte";
  import { validator } from '@felte/validator-yup';
  import * as yup from 'yup';


  const schema = yup.object({
    name:yup.string()
    .min(2,'Sorry bro, a min of 2')
    .required('Name is required :*'),
    age: yup.number().required('Age is required :*')
  })

  const { form, errors } = createForm({
    onSubmit:(values,context)=>{
      console.log(values)
      console.log(context)
    },
    extend: validator({schema})
    // validate:(values)=>{
    //   const errors = {}

    //   if(!values.age) errors.age = 'Age not be empty';
    //   if(!values.name) errors.name = 'Name not be empty';
    //   if(values.name &&values.name.length < 2) {
    //     errors.name = 'Must be over 2';
    //   }

    //   console.log(errors)
    //   return errors;
    // }
  })
 
</script>

<div class="container">

  <form use:form>
    <h1>My form</h1>
    <div class="mb-3">
      <label for="name" class="form-label">Name</label>
      <input type="text" class="form-control" name="name">
      {#if $errors.name}
          <span>{$errors.name}</span>
      {/if}
    </div>

    <div class="mb-3">
      <label for="age" class="form-label">Age</label>
      <input type="number" class="form-control" name="age">
      {#if $errors.age}
          <span>{$errors.age}</span>
      {/if}
    </div>

    <button type="submit">submit</button>

  </form>
</div>