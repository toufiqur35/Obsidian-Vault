 * Overriding works for inheritance relationship 
 * When child class change his parent properties , that is overriding 
 
 ```js
 class Father { 
 first_name='Jhon' 
 last_name='Dee' 
 getName() {
  return (`The name of the person is ${this.first_name} ${this.last_name}`) 
  } 
  } 
  class Son extends Father{ 
  first_name='Jhon Junior' 
  } 
  const SonObj = new Son(); 
  console.log(SonObj.getName());

// OutPut:
// The name of the person is Jhon Junior Dee
```