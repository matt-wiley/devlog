---

---


# Advanced Web Development Quiz 

- [frontendmasters.com - Advanced Web Development Quiz](https://frontendmasters.com/courses/web-dev-quiz/)

## Q1: `async` & `defer`

- render blocking
    - HTML parser sees a need to download a script
    - rendering stops
    - the script is fetched 
    - the script is executed 
    - rendering continues
    - in synchronous usage this will all happen on the main thread and slow down rendering; then DOM cannot be fully loaded until all fetches and executions are complete

- `async`
    - using `async` allows the fetching of the script to happen off the main thread
    - script will be executed immediately, once downloaded
    - exection still happens on the main thread and may interrupt rendering (HTML Parsing / DOM Loading)
    - **NOTE:** no guaranteed execution timing, or ordering

- `defer`
    - using `defer` also allows the fetching to occur off the main thread, but it additional suspends script execution until the DOM has fully loaded
        - this prevents render blocking
    - **IMPORTANT:**
        - when both `async` and `defer` are provided, `async` will take precedence in browser that support it 

