---

---
# Frontend Masters - Advanced Web Development Quiz 

- [frontendmasters.com - Advanced Web Development Quiz](https://frontendmasters.com/courses/web-dev-quiz/)

## Q1: `async` & `defer`

- render blocking
    - HTML parser sees a need to download a script
    - rendering stops
    - the script is fetched 
    - the script is executed 
    - rendering continues
    - in synchronous usage this will all happen on the main thread and slow down rendering; the DOM cannot be fully loaded until all fetches and executions are complete

- `async`
    - using `async` allows the fetching of the script to happen off the main thread
    - script will be executed immediately, once downloaded
    - execution still happens on the main thread and may interrupt rendering (HTML Parsing / DOM Loading)
    - **NOTE:** no guaranteed execution timing, or ordering

- `defer`
    - using `defer` also allows the fetching to occur off the main thread, but it additional suspends script execution until the DOM has fully loaded
        - this prevents render blocking
    - **IMPORTANT:**
        - when both `async` and `defer` are provided, `async` will take precedence in browser that support it 


## Q2: Render Pipeline & Compositing

- DOM Tree
    - A tree (graph) representation of the structural markup

- CSSOM Tree 
    - A tree (graph) representation of the stylesheets

- The render tree contains the combination of **VISIBLE** elements from the DOM and CSSOM trees

- Layout
    - shape, placement, and size for each layer (z-index)

- Paint (Render)
    - colors applied to pixels

- Compositing 
    - combining painted layers of the final layouts to a single presentable bitmap for display to the user
    - handled on a separate GPU-based compositor thread


## Q3: Resolving Domain Requests

- TODO

## Q4: Call Stack and Event Loop

- Call Stack
    - Stack of execution contexts for running logic

- Web API 
    - Extension of the JavaScript api that enables Web functionality 
    - `fetch`
    - `setTimeout`
    - `setInterval`

- Macrotask Queue
    - `setTimeout` callbacks
    - `setInterval` callbacks 
    - UI rendering tasks
    - User input events
    - Network events

- Microtask Queue
    - Promise callbacks 
    - `queueMicrotask` callbacks 
    - `async` / `await` 
    - `MutationObserver` callbacks

- Event Loop
    - Responsible for running tasks from the task queue 
    - Microtask queue is cleared first (`Promises` and `async`/`await`)
    - Macrotask queue is cleared when the Microtask queue is empty


### `new Promise()`

> [!IMPORTANT] 
> Promises are executed synchronously.

These are equivalent:

```
console.log("Hello right now!")
```

```
new Promise(() => { console.log("Hello right now!") })
```

In the quiz question, the following is presented with the question "what is the output in the console?" 

``` 
setTimeout(() => console.log(1) );
Promise.resolve().then(() => console.log(2) );
Promise.resolve().then(setTimeout(() => console.log(3) ));
new Promise(() => console.log(4) );
setTimeout(() => console.log(5) );
```

The output is

```
4 
2 
1 
5 
3
```
