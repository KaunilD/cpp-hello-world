# Hello World in C++

The point of this assignment is to go through the process of writing,
compiling, and submitting a simple C++ program as a homework
assignment. The implementation is quite trivial; the difficulty will
be in going through the process, which is new to all of you. (And us!)

### What we are going to do

There are three __main__ parts to doing this homework. 

__A.__ Get your environment set up so you can edit, and build the
   source code, and be able to run (execute) the program that you've
   built.  
__B.__ Be able to run the Python grading script.  
__C.__ Implement a super simple function and submit your `hello.cpp` file
   for grading.  

# Part A: Setting up your environment.

### Overview: Say Hello World

In the file `hello.cpp`, we will implement the `say_hello_world` function so it prints "Hello World!" (or whatever you'd like) to standard output. You'll do this with some combination of `cout`, `endl`, and one of the ways to indicate namespace (`using namespace std` or `std::`). 
Then we will make the project and run your executable from the command line.  
Entire process should look something like this.

``` bash
$ cd path/to/cpp-hello-world
cpp-hello-world $ make hello_main
c++ -g -Wall -Wextra -std=c++11   -c -o hello.o hello.cpp
hello.cpp:10:1: warning: control reaches end of non-void function [-Wreturn-type]
}
^
1 warning generated.
c++  -g -Wall -Wextra -std=c++11 -o hello_main hello.o hello_main.o
cpp-hello-world $ ./hello_main
Hello World!
```

### A.1: Navigating to the cpp-hello-world folder in Terminal.

First we will type the following command into the terminal.

``` bash
cd path/to/cpp-hello-world
```

There are two parts to the above command:
__1.__ cd: This is a command which stands for "Change Directory".  
__2.__ path/to/cpp-hello-world: This is the path to the cpp-hello-world folder that you just downloaded. In case of Windows the folder must be in Downloads directory.

What you did above is similar to  navigating _File Explorer_ in Windows (or _Finder_ if you use a Mac). But instead of using mouse/trackpad we will use commands typed using our keyboard.
After you've changed directories, your terminal might show your new location by changing the prompt to something like `cpp-hello-world $`.

If you dont' know where you are, type `pwd` (stands for present working directory) and it will tell you.

### A.2: Build the binary

Next, you will type the follwing command:
```bash
make hello_main
```

The above command has two parts:
__1.__ make: The make command compiles and builds the executable that is mentioned in the `Makefile`. It assumes that there is a `Makefile` present in the directory that `make` command is called in.
__2.__ hello\_main: This lets the make command know that it only has to compile and build the file specified by the __target__ `hello_main`. In absence of `hello_main` simply compiles all the default target mentioned in the `Makefile` (We will get back to this in __Part B__). 

Reading through the Makefile might make you confused at the moment; just trust me, there's a reason for it.

When `make` is done building, and assuming there are no syntax errors, it will create a new file called `hello_main` (without `.cpp` or anything else), and that's your program!

### A.3: Run (execute) the program

In order to execute the program that `make` built for us in step __A.2__ we will type the follwoing commnand in the terminal.
```bash
./hello_main
```

This will run your program, and if you've filled out the `say_hello_world` function correctly it will
print out "Hello World!" or similar.

What's the dot and slash about? That means "look for a file in the current directory". This is needed because the terminal will only look for executable files in certain locations. If you use the dot slash in front of your program name, it will look in your current directory. Further explanation would be super long-winded, so like the `Makefile` bit, I'll just leave it at that.

### A.4: Does it work?

Make sure you get this part to work and your termianl looks something like you saw in section __A.1__. This is a sanity check that you can edit, build, and run C++ programs.  

Get the pattern into your head: edit, build, run. 

Summarizing how to do this in the command line:

1. Make sure you're in the right place (so use `cd` and `pwd`).
2. Build your program with `make <target>` or just `make` if you're
   building the default target.
3. Run your program with `./some_program_name`, using dot-slash in
   front.

# Part B: Run the tests

OK, if you've done the above to your satisfaction, go ahead and move on to the next thing. But before you edit `hello.cpp` again, let's first run the grading script so you can see it what it looks like when it fails.

```bash
$ make
$ python grade.py hello_test
sanity               10 / 10
greeting             0  / 10
===============================
TOTAL                10 / 20
Command line(s) to invoke specific failed unit tests follow this message. They
will give you much more detailed information about what's wrong with your program.

./hello_test "[greeting]"
50
```

Here is what you did above:

On the first line, by typing `$ make`, you build the project with the default target (that's why you just type "make" with nothing after it). It might give you some warnings; those are OK since they don't prevent it from giving you an executable to run.

On the second line, `$ python grade.py hello_test` you run a python script and have it run `hello_test` in a few ways, and it collects data about the outcomes. This homework is boring, because there are only two tests: "sanity" always gives 10/10 points, and "greeting" will give you 10 points once you've implemented it.

I'll call your attention to the last few lines there. It says some tests fail, and you can get more info by typing certain commands. In this case, that command is `./hello_test "[greeting]"` -- complete with dot slash and double quotes and square brackets. Go ahead and try it out. When you do that, you're running a specific unit test, and you'll likely need to do that a lot in the weeks to come.

So, having seen what it looks like when you're not done yet, let's finish it up!

# Part 3: Implement `get_greeting()`

Open up your `hello.cpp` file and have it return the string Hello!". Really, that's all you need to do. 

Once you've added your little line of code to `hello.cpp`, let's re-build and run the grading script again!

```bash
$ make
c++ -g -Wall -Wextra -std=c++11   -c -o hello.o hello.cpp
c++  -g -Wall -Wextra -std=c++11 -o hello_test hello.o hello_test.o
$ python grade.py hello_test
sanity               10 / 10
greeting             10 / 10
===============================
TOTAL                20 / 20
You should be good to submit your assignment now!
100
```

So, heed the feedback. Go ahead and submit! You'll just need to submit the `hello.cpp` file.
