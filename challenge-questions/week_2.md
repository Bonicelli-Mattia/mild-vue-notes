# Week 1 Whacks

### What is the purpose of having a database? Why can't we use a file?
`A database lets us store our data in a convenient, manipulatable format, we can furthermore restrict access based on our company's access policies.`

### Schema Design
Explain what type of relationship (One-to-Many, Many-to-Many, One-to-One) you would use to represent each case, and _why_ (the _why_ is the most important): 

- UN representative <-> Country.
Relationship—`One-to-Many`
Why?—`Each country elects a single spokeperson, that represents multiple citizens`

- Car model <-> Manufacturer
Relationship—`Many-to-Many`
Why?—`A car model has parts made from different manufacturers, and different manufacturers supply multiple car models`

- Author <-> Blog post
Relationship—`One-to-One`
Why?—`A blog post is written by a single author (in most cases)` 

### Promises
Run the following code in your head and try to guess its result. Then run it on the console (devTools), and explain the result in terms of the stack, task, and microtask queue.

Your guess—`12536` 
Your console result—`12563 undefined`
Why?—`first we log 1, it gets pushed to the stack and cleared, then we run xoo() if the promise resolves it logs the value passed in, if it rejects it's going to log and exit. xoo runs and pushes log(2) on the stack, then puts in the task queue log(3) and a rejection for log(4) then pushes log(5) on the stack, 7-8-9 are not going to be logged because of the .catch() getting triggered by the reject(4). While this is happening log(6) is read outside the function and is pushed onto the stack. At this point the stack starts to get cleared, 2 and 5 are popped, then once the stack is empty the event loop starts pushing the logs from the task queue to the stack one by one waiting for the stack to clear each time. We have our log(3)appearing and an undefined caused by the reject` 

⚠️ Don't answer lightly. Your submission won't get a thumbs up until your answer is deemed clear enough by an instructor!

```js
console.log(1);

xoo()
  .then(console.log)
  .catch(console.log);

console.log(6);

function xoo() {
  return new Promise((resolve, reject) => {
    console.log(2);
    resolve(3);
    reject(4);
    console.log(5);
    resolve(7);
    resolve(8);
    resolve(9);
  });
};