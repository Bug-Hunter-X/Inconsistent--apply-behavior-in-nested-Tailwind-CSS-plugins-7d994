# Inconsistent @apply behavior in nested Tailwind CSS plugins

This repository demonstrates a bug encountered when using Tailwind CSS's `@apply` directive within nested plugins. The `@apply` directive, while powerful, exhibits unexpected behavior when used in a plugin that imports or extends another plugin also using `@apply`.

## Problem

The core issue is that `@apply` directives within nested plugins may be ignored or applied incorrectly, resulting in inconsistent styling across the application. This occurs specifically when `@apply` targets utility classes defined in the base Tailwind configuration, extended plugins, or other parts of the project.

## Reproduction Steps

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the build process (instructions may vary depending on your setup).
4. Observe the rendered output.  The expected styling will not be applied due to the misbehavior of the nested `@apply`.

## Solution

The solution involves refactoring plugin structures to avoid nested `@apply` in problematic ways, perhaps by rethinking the plugin design to be more modular, using composition over inheritance, or consolidating utility classes.  Sometimes, a more explicit approach, without relying on `@apply`, is necessary.

## Additional Notes

This bug might be specific to certain Tailwind CSS versions or configurations.  Providing more context around your setup could help in identifying the root cause and finding a solution.