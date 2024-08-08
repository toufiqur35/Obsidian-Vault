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

export default {
  setup() {
    const formSchema = yup.object().shape({
      name: yup.string().required('Name is required'),
      email: yup
        .string()
        .email('Invalid email format')
        .required('Email is required'),
      message: yup.string().required('Message is required'),
    });

    const { handleSubmit, errors, formData } = useForm({
      validationSchema: formSchema,
    });
    
    const onSubmit = () => {
      console.log(formData.value);
    };

    return {
      formData,
      errors,
      handleSubmit: handleSubmit(onSubmit),
    };
  },
};
</script>


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

#### Explanation

- **`vee-validate` and `yup`**: Used for form validation.
- **`formSchema`**: Defines the validation rules using `yup`.
- **`handleSubmit`**: Calls the `onSubmit` function when the form is valid.
- **`errors`**: Contains validation errors for each form field.

### Advanced Form Handling

#### Using Composition API for Form Management
Here’s an example of how to use the Composition API for more complex forms.

```vue
<template>
  <form @submit.prevent="handleSubmit">
    <div>
      <label for="username">Username:</label>
      <input
        id="username"
        v-model="form.username"
        type="text"
        @blur="validateField('username')"
      />
      <span v-if="errors.username">{{ errors.username }}</span>
    </div>
    <div>
      <label for="password">Password:</label>
      <input
        id="password"
        v-model="form.password"
        type="password"
        @blur="validateField('password')"
      />
      <span v-if="errors.password">{{ errors.password }}</span>
    </div>
    <div>
      <label for="confirmPassword">Confirm Password:</label>
      <input
        id="confirmPassword"
        v-model="form.confirmPassword"
        type="password"
        @blur="validateField('confirmPassword')"
      />
      <span v-if="errors.confirmPassword">{{ errors.confirmPassword }}</span>
    </div>
    <button type="submit">Register</button>
  </form>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
  setup() {
    const form = reactive({
      username: '',
      password: '',
      confirmPassword: '',
    });

    const errors = ref({});

    const validateField = (field) => {
      if (field === 'username' && !form.username) {
        errors.value.username = 'Username is required';
      } else {
        errors.value.username = '';
      }

      if (field === 'password' && !form.password) {
        errors.value.password = 'Password is required';
      } else if (field === 'password' && form.password.length < 6) {
        errors.value.password = 'Password must be at least 6 characters';
      } else {
        errors.value.password = '';
      }

      if (field === 'confirmPassword' && form.confirmPassword !== form.password) {
        errors.value.confirmPassword = 'Passwords do not match';
      } else {
        errors.value.confirmPassword = '';
      }
    };


    const handleSubmit = () => {
      Object.keys(form).forEach((field) => validateField(field));
      if (!Object.values(errors.value).some((error) => error)) {
        console.log('Form submitted:', form);
      }
    };

    return {
      form,
      errors,
      handleSubmit,
      validateField,
    };
  },
};

</script>
```