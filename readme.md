# Template: NPM Package

This is a [template repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) which you can use to quickly bootstrap your own NPM package.

## Features

- **Static Typing**: Uses [TypeScript](https://www.typescriptlang.org/) for improved type safety and a better developer experience
- **Testing**: Pre-configured [Jest](https://jestjs.io/) setup for writing and running unit tests efficiently
- **Linting**: Leverages [ESLint](https://eslint.org/) to catch potential bugs and enforce coding standards
- **Auto-Formatting**: Ensures consistent code style with automated formatting using [Prettier](https://prettier.io/)
- **Continuous Integration (CI)**: Pre-configured [Github Actions](https://docs.github.com/en/actions) for linting, testing, building, and formatting in CI environments
- **Git Hooks**: [Husky](https://typicode.github.io/husky/)-managed Git hooks to run scripts before commits, pushes, and other Git actions, ensuring code quality
- **Automated Release**: Automates versioning and package publishing via [Semantic Release](https://semantic-release.gitbook.io/semantic-release)

## Table of Content

- [Quick Start](#quick-start)
- [Tools](#tools)
  - [Typescript](#typescript)
  - [Jest](#jest)
  - [ESLint](#eslint)
  - [Prettier](#prettier)
  - [Github Actions](#github-actions)
  - [Husky](#husky)
  - [Semantic Release](#semantic-release)

## Quick Start

#### 1. Clone the template

The fastest way is to use Github CLI:

```bash
# Create a new repository using a template and clone it
gh repo create new-repo-name --template serohman/npm-typescript-module
gh repo clone new-repo-name
```
Or refer to the [official guide](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template)  for creating repositories from a template.

#### 2. Set Up NPM Authentication

You need to generate an [NPM access token](https://docs.npmjs.com/about-access-tokens) and save it as a [Github Action Secret](https://docs.github.com/en/actions/security-for-github-actions/security-guides/using-secrets-in-github-actions), under the key name `NPM_TOKEN`

Use Github CLI

```bash
# A prompt for entering the npm token will appear after the command
gh secret set NPM_TOKEN
```
Or set the secret via the web UI by navigating to your repository's GitHub page, and then: `Settings > Secrets and variables > Actions > New repository secret`.
#### 3. Instal dependencies

```bash
npm install
```

#### 4. Update `package.json` fields
Open `package.json` and fill out all the relevant fields:
- `name`
- `author`
- `description`
- `tags`
- `license`
- `publishConfig.access` (Set to `private` to make your package private)

#### 5. Publish your package

To publish your package, switch to the `release` branch, then create and push a [semantic commit](https://github.com/semantic-release/semantic-release?tab=readme-ov-file#commit-message-format) with the changes you've made to `package.json`. Once the changes are pushed, GitHub Actions will automatically publish your package.

```bash
git checkout -b "release"
git stage .
git commit -m "feat: Setup package"
git push --set-upstream origin release
```

And voilà!🎉 The moment new changes hit the release branch, GitHub Actions will pick them up and publish a new release on NPM.

## Tools

### Typescript

### Jest

### ESLint

### Prettier

### Github Actions

### Husky

### Semantic Release
