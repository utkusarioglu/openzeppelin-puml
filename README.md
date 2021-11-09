# PlantUML diagrams for OpenZeppelin contracts

OpenZeppelin contracts diagrams written in PlantUML.

## Usage

You can clone this repo as a submodule and reference it using `!include` or
`!includesub`.

## Notes on conventions

Uml lacks conventions for some of the commonly used features of solidity. These
include concepts such as modifiers, external access, events, errors and a bunch
of others.

Because of the above, we had to come up with a convention that could predictably
and easily represent solidity concepts while staying close to UML as much as
possible. With some recommendations from
[Marchesi et al.](https://arxiv.org/ftp/arxiv/papers/1809/1809.09596.pdf), we
came up with the following rules:

- External attributes will be represented with the symbol `*`
- Modifiers are prefixed with the symbol `@` to liken them to decorators in many
  popular languages. Their visibility is set set as private through `-`.
- Modifiers are applied as stereotypes. As an example `@onlyOwner()` would be
  applied as `void foo() <<onlyOwner>>`. If the modifier requires params, the
  stereotype is declared with parentheses like a normal function declaration.
- Immutable types use the stereotype `<<constant>>`
- Events are declared as `object <<event>>`
- Errors are declared as `object <<error>>`
- Structs are declared as `object <<struct>>`
- Contracts are declared as `class <<contract>>`
- Libraries are declared as `class <<library>>`

If you have any ideas on better representation of these concepts, please open an
issue or send a pull request.

## Devcontainer

We use devcontainers to isolate our projects. PlantUML requires a java
environment and we chose to include the code for the container even though its
usage is not necessary for this repo.
