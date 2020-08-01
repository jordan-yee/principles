# Kakoune Plugins
Principles to use when developing plugins for the Kakoune text editor.

TODO: Convert this list into a ToC
- Design Principles
  - Composability
  - Utility
  - Ergonomics > Motion > Pnuemonics
  - Interface before implementation
  - Polymorphic behavior
  - Just Works
  - Graceful degradation
- Uncategorized Concepts
  - On Specificity
  - Aliases vs Mappings

## Design Principles

### Composability
A specific operation should combine well with other operations to create
useful compound operations.

### Utility
A specific operation should be able to applied to a wide range of use cases.

### Ergonomics > Motion > Pnuemonics
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

**Pnuemonics** refers to associating a command with the initial letter of the
command's name to make it easier to remember. There is a lot to remember when
using any decent text editor, so making a command easier to remember is a good
thing. However, prioritizing pnuemonic bindings will result in some clunky key
combinations, which should be avoided. Further, Kakoune's mode system provides
menus that display available key bindings in an activated mode, so learning a
new key combination is a breeze.

### Interface before implementation
When designing a new plugin, you should start with the ideal set of commands
you would like the plugin to have, and then go about figuring out how to
implement them, rather than basing your functionality on how you think you'd
implement a solution off the top of your head.

### Graceful degradation
TODO

### Polymorphic behavior
TODO

### Just Works
TODO

## Uncategorized Concepts

### On Specificity
- When adding mappings or aliases to make some operation more convenient,
  it's important to keep in mind how easily a task can be done using default
  behavior. Saving a single keystroke may not be worth the overhead of adding
  a new key combination to remember.
- "It is better to have 100 functions operate on one data structure than to
   have 10 functions operate on 10 data structures." -Alan Perlis
  - It is better to have 100 mappings operate on any text file than to have 10
    mappings operate on 10 filetypes.

### Aliases vs Mappings
TODO
When should an alias be provided instead of a mapping?
