# Development Overview

## Development Tools

The [`package.json`](../../package.json) in this project's root specifies several directives used to run package 
scripts. These are outlined below in the following sections below. In general, the development flow looks something 
like:

```shell
nvm use
npm i
npm run lint:fix
npm run format:fix
npm build
```

### Linting

#### ESLint

This package is configured with [ES Lint](https://eslint.org/) to lint and fix files specified using the
configuration rules in [`.eslintrc.js`](../../.eslintrc.js), which specify several code style rules, including
popular style guides (i.e. [AirBnb](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb)),
and configurations for React.

#### Audit

The audit script audits source files for lint problems and provides an output specifying them:

```shell
npm run lint:audit
```

#### Fix

The fix script fixes lint problems in source files in place:

**Note:** It is recommended to run the audit script (i.e. `npm run lint:audit`) before running the lint script on
source files.

```shell
npm run lint:fix
```

### Formatting

#### Prettier

All `src` files are formatted using [Prettier](https://www.npmjs.com/package/prettier). Prettier options are 
configured in a root configuration file at [`.prettierrc`](../../.prettierrc), which specifies code formats such as 
line width and quotes.

#### Audit

To run a formatting audit on source files, the following command can be invoked, which will specify which (if any) 
source files contain formatting issues:

```shell
npm run format:audit
```

#### Fix

To fix source files in place using Prettier, the following command can be run:

**Note**: It is recommended to use the audit command before doing so (i.e. `npm run format:audit`)

```shell
npm run format:fix
```