---
Status: Active
Champions: @43081j
PR:
---

# Official postcss/tailwind support

As part of unifying the standard tools around lit, it would make sense to move
the [postcss-lit](https://github.com/43081j/postcss-lit) project into the
lit monorepo as an official solution to inline CSS transforms (e.g. tailwind).

## Objective

A strategy for how we will move the project into the monorepo.

### Goals
- Moving the postcss-lit project into the lit monorepo
- Potentially documenting the project in an appropriate place (or a blog post)

### Non-Goals
- Transfer of responsibility (it is expected I will continue being the primary
maintainer to avoid extra burden on the lit team)

## Motivation

The project already functions well and has high usage, but could benefit hugely
in terms of discovery and support by being in the monorepo.

- **Discovery:** we are regularly asked by users how to integrate lit with
tailwind and other such CSS solutions. Having an officially supported and
maintained integration will make this clearer
- **Support:** we are more likely to receive community contributions through
issues and pull requests

It will also become much easier to keep the integration in sync with the
most current version of lit, as we are likely to update it in line with
any breaking changes elsewhere in the monorepo.

## Detailed Design

We should be able to migrate the repository to `packages/postcss-lit`, similar
to what we will eventually do with `eslint-plugin-lit`.

Alternatively, both could live in the `labs/` project although that may not
make sense since they are both stable projects.

It is likely we want to maintain the same `postcss-lit` name just to avoid
breaking existing setups and to remain consistent with postcss' other custom
syntaxes.

## Implementation Considerations

### Implementation Plan

A single PR should be enough to begin with: copying the existing sources
to the agreed directory and ensuring CI is setup correctly.

### Backward Compatibility

N/A

### Testing Plan

Existing tests should be enough once copied across.

### Performance and Code Size Impact

N/A

### Interoperability

N/A

### Security Impact

N/A

### Documentation Plan

We should create blog posts explaining the two ways users can transform
CSS:

- Inline CSS via postcss-lit
- External CSS via rollup plugins (using CSS imports)

These could be linked in the lit website.

Alternatively, we could document both solutions in the lit website entirely
rather than blog posts.

## Downsides

N/A

## Alternatives

N/A