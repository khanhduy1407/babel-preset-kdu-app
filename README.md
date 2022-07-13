# babel-preset-kdu-app

## Features

- Latest ECMAScript features (babel-preset-env)
- Object rest spread and dynamic import
- Transform Kdu JSX
- Transform `generator` and `async/await`

## Install

```bash
yarn add babel-preset-kdu-app --dev
```

## Usage

```js
// .babelrc
{
  "presets": ["kdu-app"]
}
```

## Options

### useBuiltIns

Type: `boolean`<br>
Default: `false`

Disable runtime transform. i.e. do not add helpers and polyfill for unsupported features of target environment, eg: `Object.assign`, `Promise`

As we're using `babel-plugin-transform-runtime` to polyfill your code without polluting globals, something like `"foobar".includes("foo")` will not work since that would require modification of existing builtins. See [babel-plugin-transform-runtime](https://www.npmjs.com/package/babel-plugin-transform-runtime).

### targets

Type: `object`<br>
Default: `{ ie: 9, uglify: true }`

Takes an object of environment versions to support.

As we're using `babel-preset-env` to determine the Babel plugins and polyfills you need, this option lets you adjust your supported environments. See `targets` in [babel-preset-env](https://github.com/babel/babel-preset-env).

Note: when env is "test" `targets` is always `{ node: 'current' }`.

## License

MIT.
