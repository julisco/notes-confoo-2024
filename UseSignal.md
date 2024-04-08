# Use signal

by Ruby Jane Cabagnot

## Signals

- reactive way to update values that can change
- performance

Signals were used first in Knockout, and the in SolidJs

Frameworks using signals: SolidJs, Qwik, Vue, Svelte...

For React we need to add an additional package.

## Advantages

- maintains broadcast with the last updated values
- keep values up & sync while any of its values changes
- no re-rendering strategy
- intuitive ans minimal api
- predictability
- direct denpendency tracking

## Principle

- signals & subscribers

setter -> (update) -> SIGNAL -> (access) getter

- side effect free
- subscribers only update components that need it
