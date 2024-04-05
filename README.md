# x
 
A command line todo utility

Inspired by [Steve Losh](https://stevelosh.com/)'s [t](https://github.com/sjl/t).

I made this because I really like Steve's `t` but I wanted:

  - nice, big checkboxes
  - to see completed tasks
  - tasks always printed after every command
  - identify tasks by their text (partial match)
  - multiple lists with the same command
  - a pure bash implementation

## Install

Copy the source of [`x`](./x) into a file called `x` (or whatever you want) and
save it in some directory that exists in your `PATH`.

## Quick start

### Managing tasks

#### Create some tasks

```shell
$ x Play 5 or 6 hours of video games
[ ] Play 5 or 6 hours of video games
$ x Walk the dog
[ ] Walk the dog
```

A file called `todo` will be created in `~/todos`.  You can customize this
directory by exporting `X_TODO_DIR`.

#### List all tasks

```shell
$ x
[ ] Play 5 or 6 hours of video games
[ ] Walk the dog
```

#### Finish a task

```shell
$ x -x dog
[ ] Play 5 or 6 hours of video games
[x] Walk the dog
```

`x` just matches on some substring of your task name.

#### Purge completed tasks 

```shell
$ x -p
[ ] Play 5 or 6 hours of video games
```

### Managing task lists

#### Create a new task list

```shell
$ x -n some_list
```

#### List task lists

```shell
$ x -l
* some_list
  todo
```

#### Switch to a different list

```shell
$ x -c todo # "c" as in "current"
```

### All commands

```shell
$ x -h
x             List all tasks for current list
x Some item   Add task called "Some item" to the current list
x -x "item"   Check off the task containing "item"
x -X "item"   Uncheck the task containing "item"
x -d "item"   Delete task containing "item"
x -S          Sorts the current list
x -p          Purge completed tasks in the current list
x -n          Create a new todo list
x -l          Print all todo lists
x -c list     Make <list> the current list
x -t          Print uncompleted tasks only
x -T          Print completed tasks only
x -s          Print the status for the current list
x -e          Opens the todo file in $EDITOR
```
