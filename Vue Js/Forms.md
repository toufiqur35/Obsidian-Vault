### Basic Form Handling
Handling forms in Vue 3 can be done using the `v-model` directive, which provides two-way data binding between the form input elements and your data model.

```vue
<script> 
import { ref } from 'vue'; 
export default { setup() { 
		const formData = ref({ 
			name: '',
			email: '', 
			message: '', 
		}); 
		const handleSubmit = () => { 
			console.log(formData.value); 
		}; 
		return { 
		formData, handleSubmit, 
		}; 
	}, 
}; 
</script>

<template> 
	<form @submit.prevent="handleSubmit"> 
		<div> 
			<label for="name">Name:</label> 
			<input id="name" v-model="formData.name" type="text" /> 
		</div> 
		<div> 
			<label for="email">Email:</label> 
			<input id="email" v-model="formData.email" type="email" /> 
		</div> 
		<div> 
			<label for="message">Message:</label> 
			<textarea id="message" v-model="formData.message"></textarea> 
		</div> 
		<button type="submit">Submit</button> 
	</form> 
</template> 
```

#### Explanation
- **`v-model`**: Binds the value of the form inputs to the `formData` object.
- **`@submit.prevent`**: Prevents the default form submission behavior and calls the `handleSubmit` method instead.
- **`handleSubmit`**: Logs the form data to the console.

### Form Validation
Vue.js 3 can use various libraries to handle form validation, such as `VeeValidate` or `VueUse`. Here’s how to implement validation using `VeeValidate`.
#### Example: Form with Validation Using VeeValidate

```vue
<script> 
import { ref } from 'vue'; 
import { useForm } from 'vee-validate'; 
import * as yup from 'yup'; 
export default { setup() { const formSchema = yup.object().shape({ name: yup.string().required('Name is required'), email: yup .string() .email('Invalid email format') .required('Email is required'), message: yup.string().required('Message is required'), }); const { handleSubmit, errors, formData } = useForm({ validationSchema: formSchema, }); const onSubmit = () => { console.log(formData.value); }; return { formData, errors, handleSubmit: handleSubmit(onSubmit), }; }, }; </script>
<template> 
<form @submit.prevent="handleSubmit"> 
<div> 
<label for="name">Name:</label> 
<input id="name" v-model="formData.name" type="text" /> 
<span v-if="errors.name">{{ errors.name }}</span> 
</div> 
<div> 
<label for="email">Email:</label> 
<input id="email" v-model="formData.email" type="email" /> 
<span v-if="errors.email">{{ errors.email }}</span> 
</div> 
<div> 
<label for="message">Message:</label> 
<textarea id="message" v-model="formData.message"></textarea> 
<span v-if="errors.message">{{ errors.message }}</span> 
</div> 
<button type="submit">Submit</button> 
</form> 
</template> 
```