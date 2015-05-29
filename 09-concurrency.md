Concurrency and Parallelism in JavaScript by [Naveed Ihsanullah](http://twitter.com/naveedi)
---

- **Parallelism** & **Concurrency** are not the same
- *1995*: JavaScript invented. Home pages never the same again!
- Its harder to make CPUs faster than they are right now: with future hardware, we're adding additional *cores* or *execution units*
- web workers promote parallelism, but the threads are heavy

### Concurrency already exists in JS:

#### Parallel JavaScript
  - "Casual API"
  - more complex than it should be

#### postMessage()
  - Performance just isn't there
  - Can't share state

#### Buffer transfer
  - creates bottlenecks

- **Extensible Web Philosophy:** The best innovation comes from the developers themselves. [Link](https://extensiblewebmanifesto.org/)
- **master <--> worker shared buffer**
- Demo: JS Mandelbrot -- perf wins across all cores
- Demo: Unity WebGL Benchmark -- adding more cores brings us closer to native performance
- currently in nightly

[There are Better Notes Here](https://github.com/nchase/talks/blob/master/2015/jsconf/09-A.md)