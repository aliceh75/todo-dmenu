# todo-dmenu

[dmenu](https://wiki.archlinux.org/index.php/Dmenu) interface to add/remove todo entries in simple text files. Inspired by the [todo script on the suckless site](http://tools.suckless.org/dmenu/scripts/todo).

On invocation, **todo-dmenu** opens *dmenu* with the list of available todo lists (which are simple text files, stored by default in `~/.todo-dmenu/`). You can select an existing list, or create a new one by typing it's name. Upon selecting the list, **todo-dmenu** opens *demnu* showing the entries in the selected todo list.

You can enter a new todo, or delete an existing one by selecting it. **todo-dmenu** will then re-open the same file until you press escape.

If the environment variable `TODO_LIST` is set, then **todo-dmenu** will skip the list selection and directly open the given todo list. `TODO_LIST` should simply be the name of a file in the todo folder.

## Usage

- To cancel at any time, type escape;
- If environment variable `TODO_LIST` is set and not empty, todo-dmenu 
  will directly open the given todo list (the name being that of a file in the
  todo folder);
- If invoked without argument, todo-dmenu will first offer the choice of the todo
  list to use. Either select an existing list, or create a new one by typing it's
  name;
- Once in the todo list, you can:
    - Add a new todo, by entering it at the prompt. The current date/time
      will be appended to the name of the todo;
    - Remove a todo by selecting it and pressing enter.
- todo-dmenu remains in the todo list until esc is pressed


**Note**: Just pressing enter without typing anything will not cancel, it will delete the oldest todo. This is how *dmenu* selects entries. To cancel you must press escape.

Tasks are stored in text files, by default under ~/.todo-dmenu/ - anything that can't be done with this tool can be done by editing the files directly.

## Installation

**todo-dmenu** is a shell script and depends on `dmenu`, `sed`, `awk` and `grep`.

Just download the `todo-dmenu` script and invoke it with parameters you want to pass to *dmenu* (You probably will want `-i` for case insensitive.). Here is how I invoke it:

```
   TODO_LIST=work todo-dmenu -l 10 -i -fn "Arial-12" -nb "#666" -nf "#FFF"
```

(This requires dmenu with xft support - the Ubuntu version has it by default)
