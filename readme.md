![todoist-shortcuts logo](src/icon128.png)

**todoist-shortcuts** is a browser extension or greasemonkey script which adds a
bunch of keyboard shortcuts to [Todoist](https://todoist.com). Along with this
repository, it is also available from the following places:

* [ Extension for Google Chrome
    ![Chrome Users](https://img.shields.io/chrome-web-store/users/dehmghpdcahlffompjagejmgbcfahndp.svg)
    ![Chrome Rating](https://img.shields.io/chrome-web-store/rating/dehmghpdcahlffompjagejmgbcfahndp.svg)
  ](https://chrome.google.com/webstore/detail/todoist-shortcuts/dehmghpdcahlffompjagejmgbcfahndp)

* [ Extension for Mozilla Firefox
    ![Firefox Users](https://img.shields.io/amo/users/todoist-shortcuts.svg)
  ](https://addons.mozilla.org/en-US/firefox/addon/todoist-shortcuts/)

These keyboard shortcuts are directly inspired by the shortcuts used for GMail,
which, in turn were inspired by vim-like keyboard interaction. I highly
recommend enabling the advanced keyboard shortcuts if you use GMail.

So, if the choices of keypresses seem strange, stick with it! Many of the
keypresses used here can also be used in GMail or even vim (or [evil-mode] ;) ).

[evil-mode]: https://github.com/emacs-evil/evil

# Keyboard shortcuts

## Add tasks

| keys | action                                 |
| ---  | ---                                    |
| `q`  | Add task                               |
| `a`  | Add new task at the bottom of the list |
| `A`  | Add new task at the top of the list    |

See the "Task Quick Add shortcuts" section of [todoist's keyboard shortcuts
documentation](https://support.todoist.com/hc/en-us/articles/205063212) for
information about shorthands to use when adding tasks.  "Adding or editing
tasks" is also a good section to read, which includes keyboard shortcuts not
described in this document.

## Navigation

| keys           | action                                                |
| ---            | ---                                                   |
| `j` or `down`  | move cursor down                                      |
| `k` or `up`    | move cursor up                                        |
| `h` or `left`  | collapse nested at cursor                             |
| `l` or `right` | expand nested at cursor                               |
| `^`            | move cursor to first task                             |
| `$`            | move cursor to last task                              |
| `{`            | move cursor up to first section task                  |
| `}`            | move cursor down to next section                      |
| `/` or `f`     | focus search input                                    |
| `g`            | enter section navigation mode                         |
| `` ` ``        | select the next top section (including favorites)     |
| `` shift+` ``  | select the previous top section (including favorites) |

In "section navigation mode", the different selections in the left pane are
annotated with the keys to press to navigate to that section. Sometimes the
sidebar can have more than a screenful of content. While in this mode, you can
scroll the left pane down and up with `space` and `shift+space`.

When projects have sub-projects, they are automatically expanded when the
project is selected from the list. To collapse the sub-projects, just use
navigation mode to select the same project again.

## Manipulation of tasks at cursor

| keys                       | action                        |
| ---                        | ---                           |
| `enter`                    | edit task at cursor           |
| `o`                        | add task after cursor         |
| `shift+o`                  | add task before cursor        |
| `c`                        | open comments for cursor task |
| `shift+j` or `shift+down`  | move task at cursor downwards |
| `shift+k` or `shift+up`    | move task at cursor upwards   |
| `shift+l` or `shift+left`  | dedent task at cursor         |
| `shift+h` or `shift+right` | indent task at cursor         |

## Selection

| keys  | action                                |
| ---   | ---                                   |
| `x`   | add task at cursor to selection       |
| `* a` | select all tasks                      |
| `* n` | clear selection                       |
| `* 1` | add all priority 1 tasks to selection |
| `* 2` | add all priority 2 tasks to selection |
| `* 3` | add all priority 3 tasks to selection |
| `* 4` | add all priority 4 tasks to selection |
| `* h` | collapses all tasks                   |
| `* l` | expands all tasks                     |

## Manipulation of selected items

If none are selected, then these will apply to the cursor instead.

| keys   | action                            |
| ---    | ---                               |
| `t`    | schedule                          |
| `T`    | schedule cursor by editing text   |
| `d`    | done: mark task as complete       |
| `e`    | archive                           |
| `#`    | delete                            |
| `v`    | move to project via search prompt |
| `@`    | add label                         |
| `y`    | remove label                      |
| `1`    | set priority to 1                 |
| `2`    | set priority to 2                 |
| `3`    | set priority to 3                 |
| `4`    | set priority to 4                 |

Archiving a task via `e` is fairly similar to marking it complete via `d`.  Here
are the differences:

1. If the task is a child task, if you "Complete" it it will be checked and
   greyed out (and will remain in the list under the uncompleted parent task
   until the parent task is completed). If you "Archive" the child task it will
   be checked and then removed from view.

2. If the task is a Recurring Task (e.g. every day) and you "Complete Task" it
   will be scheduled for the next date of recurrence. If you "Archive Task" it
   will be completed and not recur again.

Note that the text rescheduling invoked by `T` only works for the current
cursor. Resolving this is tracked by [issue #24].

[issue #24]: https://github.com/mgsloan/todoist-shortcuts/issues/24

## Scheduling

When scheduling is opened via `t`, the following keybindings will apply:

| keys   | date         |
| ---    | ---          |
| `d`    | today        |
| `t`    | tomorrow     |
| `w`    | next week    |
| `m`    | in 1 month   |
| `r`    | remove       |

## Sorting

When viewing the inbox or a project, the following keybindings can be used to
sort the tasks:

| keys | sorted by        |
| ---  | ---              |
| `s`  | Sort by date     |
| `p`  | Sort by priority |
| `r`  | Sort by assignee |
| `n`  | Sort by name     |

## Bulk reschedule mode

| keys           | action                               |
| ---            | ---                                  |
| `* t`          | enter bulk reschedule mode           |
| `v` or `alt+v` | switch to bulk move mode (see below) |
| `escape`       | exit bulk reschedule mode            |

Once bulk move mode is entered, it will repeatedly bring up the reschedule
dialog until there are no more tasks after the cursor.  All of the normal cursor
navigation keys can be used while in this mode.

## Bulk move mode

| keys     | action                                     |
| ---      | ---                                        |
| `* v`    | enter bulk move mode                       |
| `alt+t`  | switch to bulk reschedule mode (see above) |
| `escape` | exit bulk move mode                        |

Once bulk move mode is entered, it will repeatedly bring up the move-to-project
dialog until there are no more tasks after the cursor. By holding down `alt`,
you can use the normal cursor navigation keys in this mode.

## Other

| keys            | action                                         |
| ---             | ---                                            |
| `u` or `ctrl+z` | undo                                           |
| `f` or `/`      | open search                                    |
| `shift+enter`   | clicks first link in the task the cursor is on |
| `ctrl+s`        | manually synchronize state with server         |

Note that undo only works when the "UNDO" button is visible at the bottom of the
screen. Some actions are not undo-able, such as [deletion or archiving multiple
tasks](https://github.com/mgsloan/todoist-shortcuts/issues/23)

# How to customize keyboard shortcuts

Ideally, there would be a UI for customizing keyboard shortcuts. However, it
seems like this would take a substantial amount of development effort
(PR contributions appreciated!). For now, you can do the following to customize
the keyboard shortcuts in Chrome:

1. Clone this repository (run `git clone https://github.com/mgsloan/todoist-shortcuts`)

2. Go to `chrome://extensions` in the url bar, and switch from the official
   version of todoist-shortcuts to a local version.

   - Disable the official version of todoist-shortcuts by unchecking "Enabled".

   - Click the "Developer mode" box in the top right if it is not yet checked.

   - Click the "Load unpacked extension..." button.  In the directory selecter
     navigate to the folder you cloned todoist-shortcuts to, and point it at the
     `src` sub-directory.

2. Edit `src/todoist-shortcuts.js` in a text editor.

   - You will probably just want to edit the definition of KEY_BINDINGS near the
     top.

   - To disable a keybinding, put `//` in front of it.

   - The functions in the section marked `Actions` are intended to be bound
     directly to keys.  You can also combine multiple actions via use of the
     `sequence` and `ifThenElse` action combiners.

   - Multiple key sequences can be bound to the same action by using a list of
     key sequences (like `['j', 'down']`) instead of a single string for it.
     The docs for [mousetrap](https://craig.is/killing/mice) may be helpful in
     figuring out how to express key sequences.

3. Use `ctrl+r` on `chrome://extensions`.  This causes the extension to be
   reloaded from your local files.

4. If you reload Todoist, you will now be using your modified version of the
   extension.

I'm sure there is a similar mechanism for Firefox, but I do not use it for
developing the extension, so not sure of the details.

One thing to note is that you will no longer receive automated updates.  To
update your locally modified extension, do the following:

1. `git stash` to store your changes.

2. `git pull` to fetch the most recent changes in this repository.

3. `git stash apply` to bring back your changes. This may cause merge conflicts.

See the git documentation.  A miscellaneous aside is that I highly recommend
[git from the bottom up](https://jwiegley.github.io/git-from-the-bottom-up/) as
a guide to understanding git's data model.

# Development

Contributions are appreciated. See [development.md](./development.md) for more
information about development.

# Supported by bounty from Doist company

Much of the work on this has been kindly supported by Amir Salihefendic of Doist
company. They're awesome!
