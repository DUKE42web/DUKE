# Testing Assignment

{% embed url="https://jestjs.io/docs/getting-started" %}



## Getting Started · Jest

> ### Excerpt
>
> Install Jest using yarn:

***

Install Jest using [`yarn`](https://yarnpkg.com/en/package/jest):

Or [`npm`](https://www.npmjs.com/package/jest):

```
npm install --save-dev jest
```

Note: Jest documentation uses `yarn` commands, but `npm` will also work. You can compare `yarn` and `npm` commands in the [yarn docs, here](https://yarnpkg.com/en/docs/migrating-from-npm#toc-cli-commands-comparison).

Let's get started by writing a test for a hypothetical function that adds two numbers. First, create a `sum.js` file:

```
function sum(a, b) {  return a + b;}module.exports = sum;
```

Then, create a file named `sum.test.js`. This will contain our actual test:

```
const sum = require('./sum');test('adds 1 + 2 to equal 3', () => {  expect(sum(1, 2)).toBe(3);});
```

Add the following section to your `package.json`:

```
{  "scripts": {    "test": "jest"  }}
```

Finally, run `yarn test` or `npm run test` and Jest will print this message:

```
PASS  ./sum.test.js✓ adds 1 + 2 to equal 3 (5ms)
```

**You just successfully wrote your first test using Jest!**

This test used `expect` and `toBe` to test that two values were exactly identical. To learn about the other things that Jest can test, see [Using Matchers](https://jestjs.io/docs/using-matchers).

### Running from command line

You can run Jest directly from the CLI (if it's globally available in your `PATH`, e.g. by `yarn global add jest` or `npm install jest --global`) with a variety of useful options.

Here's how to run Jest on files matching `my-test`, using `config.json` as a configuration file and display a native OS notification after the run:

```
jest my-test --notify --config=config.json
```

If you'd like to learn more about running `jest` through the command line, take a look at the [Jest CLI Options](https://jestjs.io/docs/cli) page.

### Additional Configuration

#### Generate a basic configuration file

Based on your project, Jest will ask you a few questions and will create a basic configuration file with a short description for each option:

#### Using Babel

To use [Babel](https://babeljs.io), install required dependencies via `yarn`:

```
yarn add --dev babel-jest @babel/core @babel/preset-env
```

Configure Babel to target your current version of Node by creating a `babel.config.js` file in the root of your project:

babel.config.js

```
module.exports = {  presets: [['@babel/preset-env', {targets: {node: 'current'}}]],};
```

_The ideal configuration for Babel will depend on your project._ See [Babel's docs](https://babeljs.io/docs/en/) for more details.

**Making your Babel config jest-aware**

Jest will set `process.env.NODE_ENV` to `'test'` if it's not set to something else. You can use that in your configuration to conditionally setup only the compilation needed for Jest, e.g.

babel.config.js

```
module.exports = api => {  const isTest = api.env('test');    return {      };};
```

> Note: `babel-jest` is automatically installed when installing Jest and will automatically transform files if a babel configuration exists in your project. To avoid this behavior, you can explicitly reset the `transform` configuration option:

jest.config.js

```
module.exports = {  transform: {},};
```

**Babel 6 support**

#### Using webpack

Jest can be used in projects that use [webpack](https://webpack.js.org) to manage assets, styles, and compilation. webpack does offer some unique challenges over other tools. Refer to the [webpack guide](https://jestjs.io/docs/webpack) to get started.

#### Using parcel

Jest can be used in projects that use [parcel-bundler](https://parceljs.org) to manage assets, styles, and compilation similar to webpack. Parcel requires zero configuration. Refer to the official [docs](https://parceljs.org/docs/) to get started.

#### Using TypeScript

Jest supports TypeScript, via Babel. First, make sure you followed the instructions on [using Babel](https://jestjs.io/docs/getting-started#using-babel) above. Next, install the `@babel/preset-typescript` via `yarn`:

```
yarn add --dev @babel/preset-typescript
```

Then add `@babel/preset-typescript` to the list of presets in your `babel.config.js`.

babel.config.js

```
module.exports = {  presets: [    ['@babel/preset-env', {targets: {node: 'current'}}],    '@babel/preset-typescript',  ],};
```

However, there are some [caveats](https://babeljs.io/docs/en/babel-plugin-transform-typescript#caveats) to using TypeScript with Babel. Because TypeScript support in Babel is purely transpilation, Jest will not type-check your tests as they are run. If you want that, you can use [ts-jest](https://github.com/kulshekhar/ts-jest) instead, or just run the TypeScript compiler [tsc](https://www.typescriptlang.org/docs/handbook/compiler-options.html) separately (or as part of your build process).

You may also want to install the [`@types/jest`](https://www.npmjs.com/package/@types/jest) module for the version of Jest you're using. This will help provide full typing when writing your tests with TypeScript.

> For `@types/*` modules it's recommended to try to match the version of the associated module. For example, if you are using `26.4.0` of `jest` then using `26.4.x` of `@types/jest` is ideal. In general, try to match the major (`26`) and minor (`4`) version as closely as possible.

```
yarn add --dev @types/jest
```
