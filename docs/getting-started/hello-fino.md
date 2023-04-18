---
sidebar_position: 1.3
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Hello, Fino!

:::info

This tutorial aims to be beginner-friendly to people new to Fino, or new to the functional programming paradigm. It assumes some prior programming experience.

:::

Now that we've hopefully installed Fino correctly, it's time to test out the language - with the classic *Hello, Fino!* program of course.

In this short section, we will:
- Write a simple program which prints a message
- Extend it to take in user input
- Dip our toes in a few simple but powerful features of the language
- Get an idea of how it feels to write [effectful](https://en.wikipedia.org/wiki/Side_effect_(computer_science)) code in Fino

## Writing the code

Get started by creating a new file, call it whatever you want, and preferably give it a `.fn` file extension. Open up the file in your favourite text editor and proceed by writing the following lines of code:
```(jsx title="hello-world.fn" showLineNumbers)
import prelude

fn main : unit -> unit
    () = println "Hello, Fino!"
```

Click on a tab to understand what a specific line of code does:
<Tabs>
<TabItem value="line1" label="Line 1" default>

This line imports the `prelude` module from the standard library, which in turn brings a small set of essential modules into scope, such as the `io` module which we use `println` from (on line 4).

</TabItem>
<TabItem value="line3" label="Line 3">

This line defines the variable `main` as a function which accepts a `unit` as input and evaluates to a `unit` as output. The `unit` type only has one value - `()` - so it is often used like this when a function only produces side effects and does not evaluate to anything useful (in this case, the `main` function only prints out a string).

</TabItem>
<TabItem value="line4" label="Line 4">

There's a few different things happening on this line.

First, on the left of the `=` sign is a pattern. Specifically, it is a pattern which matches the `()` literal. Pattern matching is covered in depth elsewhere in the documentation.

On the right of the `=` sign is the body of the function, the expression which is evaluated when the function is called. In this case, the expression simply consists of the function `println` being applied to a string literal. The function `println` has a type of `str -> unit`, so it takes in a `str` as input and evaluates into a `unit` as output.

</TabItem>
</Tabs>

## Running the program

As described in the previous section on usage, to compile the program use the following command:
<Tabs groupId="os-cmd">
<TabItem value="posix" label="Linux / MacOS" default>

```
fino -f hello-world.fn -o hello-world.bin
```

</TabItem>
<TabItem value="windows" label="Windows">

```
fino -f hello-world.fn -o hello-world.exe
```

</TabItem>
</Tabs>

And then simply run the executable to run the program:

<Tabs groupId="os-cmd">
<TabItem value="posix" label="Linux / MacOS" default>

```
./hello-world.bin
```

</TabItem>
<TabItem value="windows" label="Windows">

```
hello-world.exe
```

</TabItem>
</Tabs>

<br/>

You should see the following output:
```
Hello, Fino!
```

## Some more
While writing a *Hello, Fino!* program is fun, let's try exploring some more of the language. Specifically, let's extend our program to take in user input in the form of a name, and then output a greeting.

As before, create a new file, name it whatever you want, and give it a `.fn` file extension. Edit the file and write the following few lines of code:
```(jsx title="greeting.fn" showLineNumbers)
import prelude

fn main : unit -> unit
    () = do
        println "What is your name?"
        let name = input ()
        println ("Hello, " + name + "!")
```

:::note

Currently, `do` notation (and consequently `mdo`) is only a planned feature and is not implemented in the compiler yet. To actually have a working program, look at the code [below](#without-do-notation).

:::

Now we've introduced a few more language features: `do` notation, `let` bindings, and user-defined operators.

[WIP]

### Without `do` notation
Here is the same function written without `do` notation
```(jsx title="greeting.fn" showLineNumbers)
import prelude

fn main : unit -> unit
    () =
        let _ = println "What is your name?" in
        let name = input () in
        println ("Hello, " + name + "!")
```

### An exercise