# Cooperative Extensible Interfaces

## Example case

There's a software library `Lib`. `Lib`'s author adds an *extensible* "Compatibility" section to its website mentioning there some popular integrations.

A user `User` subscribes to a service `Srv` that somehow gathers compatibility information about different libraries.
`Srv` lets `User` mark the libraries/frameworks they're interested in.

When `User` opens `Lib`'s page, their browser loads `Srv`'s block into the "Compatibility" section. `Srv` shows info about `Lib`'s compatibility with `User`'s favourite libraries. `User` is happy.
