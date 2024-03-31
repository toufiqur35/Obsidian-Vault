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