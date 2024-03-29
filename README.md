# @dibop/eslint-config

my personal opinionated shareable eslint-config

## Features

The config includes these plugins by default:

- [babel](https://github.com/babel/eslint-plugin-babel)
- [eslint-comments](https://github.com/mysticatea/eslint-plugin-eslint-comments)
- [import](https://github.com/benmosher/eslint-plugin-import/issues)
- [prettier](https://github.com/prettier/eslint-plugin-prettier)
- [react](https://github.com/yannickcr/eslint-plugin-react/issues)
- [react-hooks](https://www.npmjs.com/package/eslint-plugin-react-hooks)
- [react-native](https://github.com/intellicode/eslint-plugin-react-native)
- [@typescript-eslint/eslint-plugin](https://github.com/typescript-eslint/typescript-eslint)

The config uses the `overrides` feature of ESLint to automatically adjust the config based on the filename. For example, typescript support is enabled for `.ts` and `.tsx` files, the `jest` environment is set for test files and more.

Prettier is used for formatting.

## Usage

First, install the required packages:

```sh
yarn add --dev prettier eslint @dibop/eslint-config
```

If you're using TypeScript, also install the TypeScript compiler:

```sh
yarn add --dev typescript
```

Now extend the config in `.eslintrc.json`:

```json
{
  "extends": "@dibop"
}
```
or
```json
{
  "extends": "@dibop/eslint-config"
}
```

To lint your files, you can add the following script to your `package.json`:

```json
"scripts": {
  "lint": "eslint \"**/*.{js,ts,tsx}\""
}
```

To show lint errors in your editor, you'll need to configure your editor. To configure [VSCode](https://code.visualstudio.com), add the following in `settings.json`:

```json
"eslint.validate": [
  {
    "language": "javascript",
    "autoFix": true
  },
  {
    "language": "javascriptreact",
    "autoFix": true
  },
  {
    "language": "typescript",
    "autoFix": true
  },
  {
    "language": "typescriptreact",
    "autoFix": true
  }
],
```

On Mac OS, you can open `settings.json` file from `Code` > `Preferences` > `Settings` or via the keyboard shortcut <kbd>⌘,</kbd>.

This config sets `autoFix` to `true` to automatically fix lint errors on save. You can set it to `false` if you don't want this behaviour.

Happy linting 🎉