# Writing At First
Python has a GIL so it can only use one core per process. So using multiprocessing can use more cores.
# About Python multiprocessing API
What I use is :
```
multiprocessing.Process(target = targetfunc, args = args)
```
It's to create a new object that contains a process .
`target` is to input a function that function need to be run on the process.
`args` is to input the parameters

This class has a `start` function that can make this process start to run.
