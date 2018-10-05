August 2018
==========

Tech
----


### Javascript

  - Holy grail of how V8 works internally with tips [(video)](https://www.youtube.com/watch?v=EhpmNyR2Za0) 
  
  #### [Iterations](https://youtu.be/DqMFX91ToLw?t=22m23s)
  
  - `for (const item of items){}` Access values like "he", "llo",...
  - `for (const item in items){}` Access indexes like 0,1,2,...
  - Iterator pattern: `let iterator = [42, 39][@@iterator]();` Then it can be called like `iterator.next();`. This is the syntactic sugar behind `for..of` loop
  
   #### [Function generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*) (Return multiple values, this is prior to async/await)
   
 ```
function* test(i) {
  yield i;
  yield i + 10;
}

let xyz = test(10);

console.log(xyz.next().value);
// expected output: 10

console.log(xyz.next().value);
// expected output: 20
  ```
  
 Task.js library is cool for things like this and spawn function
 
  ```
function* getStockPrice(name) {
  let symbol = yield getStockSymbol(name);
  let price = yield getStockPrice(symbol);
  return price;
}

//Spawn returns a promise ofc
spawn(getStockPrice("Apple")).
  then(
    price => console.log(price),
    error => console.log(error));
  ```
  ```
  async function getStockPrice(name){
      let symbol = await getStockSymbol(name);
      let price = await getStockPrice(symbol);
      return price;
  }
  
  let result = getStockPrice("Apple");
  result.then(console.log, console.error);
  ```
  
  #### [Observer pattern](https://youtu.be/DqMFX91ToLw?t=38m07s) (Iterates, finish and return errors everything in a controlled way)
  First option (Implementation in video)
  
  ```
  nums().observer({
    next(v) { console.log(v); },
    return(v) { console.log("done: " + v); },
    throw(e) { console.error(e); }
  });
  ```
  
  Second option
  
  ```
  nums().forEach(v => console.log(v)).
    then( v => console.log(`done: {v}`),
          e => console.error(e));
  ```
  
  Third option
  
  ```
  (async function writeNums(){
    try{
      for(let v on nums()){
        console.log(v);  
      }
    } catch(e) { console.error(e); }
    console.log("done");
  })();
  ```
  
  #### Using async with on
  
  ``` 
  async function printSpikes(){
    for(var spike on getPriceSpikes("Apple", 3.15){
      console.log(spike);
    }
  }();
  ```
