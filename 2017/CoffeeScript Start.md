# Writing At First
Because Atom uses a lot of CoffeeScript to product itself. And writing some plugins can use it through JavaScript is also allowed. So I will study it to write some Atom plugins or Chrome plugins.

# What is CoffeeScript
From Coffee.org:
> CoffeeScript is a little language that compiles into JavaScript. Underneath that awkward Java-esque patina, JavaScript has always had a gorgeous heart. CoffeeScript is an attempt to expose the good parts of JavaScript in a simple way.

Also it need I to know JavaScript. And I know a little. I think it is enough.

# About its grammar
I think its grammar likes Python.
## Define a variable
Like this:
```
a = 0
b = "i"
```
And after compiling, its JavaScript code like this:
```
var a, b;

a = 0;

b = "i";
```
## Define a function
Like this:
```
add = (a,b) -> a+b
multiply = (a,b) -> a*b
```
And after compiling, its JavaScript code like this:
```
var add, multiply;

add = function(a, b) {
  return a + b;
};

multiply = function(a, b) {
  return a * b;
};
```
## Using if
Like this:
```
a = 1
if a=0
    a++
```
Compiles to JavaScript:
```
var a;

a = 1;

if (a = 0) {
  a++;
}
```
## Using for
```
for a in [1..10]
    alert(a)
```

```
var a, i;

for (a = i = 1; i <= 10; a = ++i) {
  alert(a);
}
```
