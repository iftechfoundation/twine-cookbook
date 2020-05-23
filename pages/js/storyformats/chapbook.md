# Chapbook JavaScript

Chapbook enables JavaScript support through its [`[JavaScript]` modifier](https://klembot.github.io/chapbook/guide/advanced/using-javascript-in-passages.html).

## Accessing Variables

Variables are normally accessed and their values changed through the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) of a passages.

Chapbook also provides the global object **engine.state** and its methods **set(variable, value)** and **get(variable)** for accessing story variables.

> **Reminder:** A *story variable* is one which exists for as long as the story is running.
>
> In Chapbook, they are defined in the Vars Section and remain until the story stops.

### State Set

The method **engine.state.set()** will either update a variable's value, if it exists, or create the variable, if it does not. (The name of the variable should be enclosed in quotation marks.)

```twee
[JavaScript]
engine.state.set('example', 'Hi!');
[continued]

{example}
```

### State Get

The method **engine.state.get()** will retrieve the value of a variable. If it does not exist, the value returned will be `undefined`.

```twee
example: "Hi!"
--

[JavaScript]
let example = engine.state.get('example');
write(example);
```

## Writing Values

Chapbook provides the function **write()** for adding values to the content of a passage inside of the `[JavaScript]` modifier.

```twee
Jolene,

Jolene,

[JavaScript]
write("Jolene,");
[continued]

Jolene.
```
