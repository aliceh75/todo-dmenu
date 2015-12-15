# todo-dmenu

[dmenu](https://wiki.archlinux.org/index.php/Dmenu) interface to add/remove todo entries in a simple text file. Inspired by the [todo script on the suckless site](http://tools.suckless.org/dmenu/scripts/todo).

On invocation, **todo-dmenu** opens *dmenu* with the list of todos previously entered (and stored in a local file, by default `~/.todo-dmenu`).

You can enter a new todo, or delete an existing one by selecting it.

## Usage

- To cancel, type escape;
- To add a new todo, just enter it at the prompt. The current date/time will be appended to the name of the todo;
- To remove a todo, select it and press enter.

**Note**: Just pressing enter without typing anything will not cancel, it will delete the oldest todo. This is how *dmenu* selects entries. To cancel you must press escape.

Todos are stored in a text file, by default `~/.todo-dmenu`. This can be edited directly, and contains one todo per line.

## Installation

**todo-dmenu** is a shell script and depends on `dmenu`, `sed`, `awk` and `grep`.

Just download the `todo-dmenu` script and invoke it with parameters you want to pass to *dmenu* (You probably will want `-i` for case insensitive.). Here is how I invoke it:

```
   todo-dmenu -l 10 -i -fn "Arial-12" -nb "#666" -nf "#FFF"
```

(This requires dmenu with xft support - the Ubuntu version has it by default)
