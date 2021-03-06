# Purescript-Halogen-Hooks-Extra

Provides useful Halogen Hooks and other utilities commonly used in hooks (e.g. actions).

## Hooks

- `useDebouncer` - run an action only when a specified amount of time has passed without receiving any new updats/values (e.g. search the database using user's query after 300 ms of no input).
- `useThrottle` - run an action with the next value after ignoring new values for a specified amount of time (e.g. handle 1 scroll event every 300 ms).
- `useEvent` - run a callback whenever a new value is pushed (e.g. allow a library to publish events within it to end-users of the library).
- Convenience function `useStateFn` and shorthand `useModifyState_` / `useModifyState` / `usePutState`. These provide a `MonadState` update function rather than a stateID. This is similar to the `react-basic-hooks` API, where `useState` in that framework behaves like `useModifyState_` here. Use these functions if you only need a single way to update state and prefer more concise code.
- `useGet` - Produce a `get` function for a value by saving the value in a mutable reference. This function behaves like the `Hooks.get` function for reading the current state. Most commonly used to get a mutable reference to component `input` so you can read the most up-to-date input when in a callback or effect cleanup.

## Actions

- Reduce boilerplate when calling `preventDefault` on mouse events and key events.

## Examples

```bash
# Compile the examples
spago -x examples.dhall bundle-app --main Examples.Main --to dist/app.js

# Then open the `dist/index.html` file in your favorite browser
# firefox dist/index.html
# google-chrome dist/index.html
```
