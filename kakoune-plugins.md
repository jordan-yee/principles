# Kakoune Plugins
Principles to use when developing plugins for the Kakoune text editor.

TODO: Convert this list into a ToC
- Design Principles
  - Composability
  - Utility
  - Ergonomics > Motion > Mnemonics
  - Interface before implementation
  - Polymorphic behavior
  - Just Works
  - Graceful degradation
  - Portability
- Uncategorized Concepts
  - On Specificity
  - Aliases vs Mappings

## Design Principles

### Composability
A specific operation should combine well with other operations to create
useful compound operations.

### Utility
A specific operation should be able to applied to a wide range of use cases.

### Ergonomics > Motion > Mnemonics
This principle is describing a priority for assigning key combinations.

**Ergonomics** refers to how efficiently and naturally the mechanics of
executing a key combination are.

**Motion** refers to associating directional movements with directional
operations. This could be applied in two ways. The first way is how the `wasd`
keys are tradionally used for forward, left, backward, and right in gaming.
This makes since because these keys are arranged in those directions relative
to each other. The second way is to associate directions with established,
directional bindings such as Vi's `hjkl`. `h` and `l` are indeed placed on
the apropriate sides, but `j` and `k` are learned associations.

**Mnemonics** refers to associating a command with the initial letter of the
command's name to make it easier to remember. There is a lot to remember when
using any decent text editor, so making a command easier to remember is a good
thing. However, prioritizing mnemonic bindings will result in some clunky key
combinations, which should be avoided. Further, Kakoune's mode system provides
menus that display available key bindings in an activated mode, so learning a
new key combination is a breeze.

### Interface before implementation
When designing a new plugin, you should start with the ideal set of commands
you would like the plugin to have, and then go about figuring out how to
implement them, rather than basing your functionality on how you think you'd
implement a solution off the top of your head.

### Graceful degradation
This principle comes can be seen in two ways:
1. If a plugin uses an external program or library, it should be written to work
   to the greatest extent possible should it be installed on a system without
   the dependency installed.
2. A plugin should be implemented in a way that exposes only as much of its
   interface as has been implemented. This allows for an interface to be
   partially implemented if the concrete dependency being used for
   implementation cannot provide what is needed for certain interface commands.

### Polymorphic behavior
If a command may have different behavior when executed on different systems or
in different contexts, it should be written to detect which implementation it
should use. If necessary, an option can be provided to set desired behavior.

Examples:
- A generic window management command should detect which window manager is
  being used to select the an implementation for that window manager.
- A `select-function` command may need to be implemented differently in different
  languages.

### Just Works
No matter how unelegant the solution, a feature that always Works and never
breaks is a good thing. Manually handling edge cases or using rediculous
work arounds to get the job done are fair game.

### Portability
Minimize external dependencies, and provide decoupled interfaces to them when
needed. Use shell script with the widest possible compatability rather than a
specific shell's script that makes things easier.

## Uncategorized Concepts

### On Specificity
- When adding mappings or aliases to make some operation more convenient,
  it's important to keep in mind how easily a task can be done using default
  behavior. Saving a single keystroke may not be worth the overhead of adding
  a new key combination to remember.
- "It is better to have 100 functions operate on one data structure than to
   have 10 functions operate on 10 data structures." -Alan Perlis
  - It is better to have 100 mappings operate on any text file than to have 10
    mappings operate on 10 filetypes. Or something.

### Aliases vs Mappings
When should an alias be provided instead of a mapping?
- New mappings should be given careful thought, and reserved for frequently
  executed actions. Saving 2 or even 10 keystrokes on an action performed
  twice a day is probably not worth it.
- When feeling like it is painful to type a particular command fully, an giving
  it an alias may be a good idea. However, try to figure out the quickest way
  to type it with auto-complete first.
- An alias can also be used to provide a generic interface command, as is the
  case with the `repl` and `send-text` command aliases.
