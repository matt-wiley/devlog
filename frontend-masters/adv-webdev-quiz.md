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
    - in synchronous usage this will all happen on the main thread and slow down rendering

- `async`
    - using `async` allows the fetching of the script to happen off the main thread
    - **NOTE:** no guarantee that the script will be executed


