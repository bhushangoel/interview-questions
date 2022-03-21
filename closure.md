# Closure
when we **return a function from any function**, the returned function carries all the **surrounding data** from where it was born in a backpack called 
`Closure`

<img width="654" alt="Screenshot 2022-03-21 at 19 19 47" src="https://user-images.githubusercontent.com/4375188/159275018-3a5bb9dd-4e72-4ce6-930d-93730e61b917.png">


```js
function createFunction(array) {
    let i=0;
    function inner() {
        const element = array[i];
        i++;
        return element;
    }
    return inner;
}

const returnNext = createFunction([4,5,6]);
console.log("here : ", returnNext);   // Closure property exists here which has {array: [4,5,6], i:0}
console.log("here : ", returnNext())  // 4
console.log("here : ", returnNext())  // 5
console.log("here : ", returnNext())  // 6
```

> Rule about what data is available to you is about where the function is born, where is is defined is known as a `lexically scoped language`.
> It means a language that says, where you defined me determines what data I have available with me when I am eventually run
