* Constructor inside only parent class
```js
class Father { 
constructor() { 
console.log('I am a constructor of Father Class') 
}
} 
class Son extends Father {
} 
const son = new Son();

//OutPut:
// I am a constructor of Father Class
```

* Constructor inside only parent class pass parameters
```js
class Father { 
constructor(msg) { 
console.log(msg) 
} 
}
class Son extends Father { 
} 
const son = new Son("This is constructor params");
const father = new Father("This is constructor params");

//OutPut:
// This is constructor params
// This is constructor params
```

* Constructor inside only child class
```js
class Father { 
} 
class Son extends Father { 
constructor() { 
super();
console.log('I am a constructor of Son Class') 
} 
} 
const son = new Son();

//OutPut:
// I am a constructor of Son Class
```

* Constructor inside only child class pass parameters
```js
class Father {
} 
class Son extends Father { 
constructor(msg) { 
super(); 
console.log(msg) 
} 
} 
const son = new Son(" I am child class constructor");

//OutPut:
// I am child class constructor
```

* Constructor inside both parent & child class
```js
class Father { 
constructor() { 
console.log('I am a constructor of Father Class') 
} 
} 
class Son extends Father { 
constructor() { 
// Always call the parent class constructor first with `super` to ensure the parent's properties are initialized. 
super(); 
console.log('I am a constructor of Son Class') 
}
} 
const son = new Son();

//OutPut:
// I am a constructor of Father Class
// I am a constructor of Son Class
```

* Constructor inside both parent & child class pass parameters
```js
class Father {
constructor(parentParams) {
console.log(parentParams) 
} 
} 

class Son extends Father { 
constructor(childParams) { 
// Always call the parent class constructor first with `super` to ensure the parent's properties are initialized. 
super(); 
console.log(childParams) 
}
} 
const son = new Son("I am child class constructor"); 
const father = new Father("I am parent class constructor");

//OutPut:
// I am child class constructor
// I am parent class constructor
```