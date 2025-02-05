# Contributing to this project

Thank you for your interest in contributing to
Pantheon's Decoupled Kit ⚡️!

## Getting started and Prerequisites

Check the [prerequisites](https://github.com/pantheon-systems/decoupled-kit-js/#prerequisites) and [getting started](https://github.com/pantheon-systems/decoupled-kit-js/#getting-started) to get setup for development.

If you find a bug or have a feature request, please open an issue or a start a discusson.

## Packages

You should be able to get started developing on the packages right away. They have a vite powered server built in to test changes made to the package, you can use the `src/main.ts` file within the package you want to contribute to.

### Adding New Modules

CMS specific modules should be created in `packages/drupal-kit` or `packages/worpress-kit` respectively.

Exports for any modules that are intended to be available within the distributed
package should be added to `index.js`.

All module code should be written in TypeScript.

### Running A Local Development Server

The `pnpm --filter './packages/{package name}' dev` can be run for local development.
It will watch for changes and launch `index.html` at http://localhost:3000. `index.html` loads
`src/main.ts` which can be used for demonstration purposes and local
development.

### Formatting and Linting

Linting and formatting will run for all staged files as a pre-commit hook.

VSCode users can format code on save using the
[Eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
and
[Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
extensions. These extensions will be suggested when loading the project if they
have not already been installed. A settings file is included in
`.vscode/settings.json`.

Formatting on save is highly recommended as it should resolve most formatting
issues before the pre-commit hook runs.

Formatting and linting can also be run manually using the following commands:

- `pnpm --filter './packages/**' lint-staged` - Runs lint-staged for packages
- `pnpm --filter './starters/**' lint` - Runs lint for starters
- `pnpm prettier -r` - Runs prettier for each package and starter
- `pnpm prettier:fix -r` - Attempts to fix any formatting issues

## Testing

This project is configured to run [Jest](https://facebook.github.io/jest/) tests
via `pnpm --filter './packages/**' test`. All new code is expected to be covered by tests and these
tests will run as part of our CI process and will also be run locally as a
pre-commit hook.

Tests should be added in a `__tests__` directory adjacent to the file they are
testing and the files should be named `<fileName>.test.ts`.

## Documentation

All new code written in packages should include [TypeDoc](https://typedoc.org/) style comments.
These comments are used to generate the API reference in `web/docs`

Some docs in this folder are manually authored.
If you believe a feature or change warrants documentation of this kind,
for example a new feature in a starter please provide it
in the appropriate place in `web/docs`

To generate documentation run `pnpm generate-docs` The result will be in the `web/docs`
folder.

The docs site can be run locally with `pnpm --filter './web' start`.

View the site at `http://localhost:3000`

TODOS:

- Confirm that this package provides types for all exported functions when used
  as an NPM package.
- Allow individual import of modules rather than requiring imports from the main
  bundle.

### Starters

To contribute to the starters, you will need a backend to develop against.

### next-drupal-starter

<!-- Instructions on how to spin up a backend for local deveopment here -->

### gatsby-wordpress-starter

<!-- Instructions on how to spin up a backend for local deveopment here -->

## Notes for Maintainers

When merging pull requests, please use the "Merge Commit" option on the pull request in GitHub.
