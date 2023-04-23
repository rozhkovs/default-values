[LICENSE]: https://github.com/rozhkovs/default-values/blob/HEAD/LICENSE
[AUTHOR]: https://github.com/rozhkovs

# 🫡 Default Values 🫡
<p>
  <a href="https://github.com/rozhkovs/default-values/blob/HEAD/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Default Values is released under the MIT license." />
  </a>
  <a href="https://github.com/rozhkovs/default-values/actions/workflows/testing.yml">
    <img src="https://github.com/rozhkovs/default-values/actions/workflows/testing.yml/badge.svg" alt="Default values passed the testing" />
  </a>
  <a href="https://www.npmjs.com/package/default-values">
    <img src="https://img.shields.io/npm/v/default-values?color=brightgreen&label=npm%20package" alt="Current npm package version." />
  </a>
</p>

This library aims to provide the most necessary default values. Stop creating variables all over the code!

## Installation
For **npm**
```shell
npm install default-values
```
For **yarn**
```shell
yarn add default-values
```

## What's the problem?
We all use some default values. And we can do it as follows:
```typescript
const myValue = someValue ?? {}; // {} - defualt value
// or
myValue ??= []; // [] - default value
// or ...
```
But sometimes we need to have a stable reference to the default value for some tasks. Let's look at the following React component.
```tsx
const ParentComponent = () => {
  // ...
  const list = listOrNull ?? [];
  return <MemoHeavyList list={list} />
}
```
If the variable 'listOrNull' is null, then each time the Parent Component function is called, the variable 'list' will have a new reference to an empty array, which will cause the 'MemoHeavyList' component rerender.

We can solve this problem as follows:
```tsx
import {EMPTY_ARRAY} from 'default-values'

const ParentComponent = () => {
  // ...
  const list = listOrNull ?? EMPTY_ARRAY; // EMPTY_ARRAY instend of [];
  return <MemoHeavyList list={list} />
}
```
For such cases, the library provides various typical variables that can be used as default values.

## Includes
- empty array: 'EMPTY_ARRAY' or 'E_ARR';
- empty object: 'EMPTY_OBJECT' or 'E_OBJ';
- empty callback: 'EMPTY_CALLBACK' or 'E_CB';

## 👨‍💻 Author
[Sergey Rozhkov][AUTHOR]

## 🎯 Was it helpful?

Do you like it and find it helpful? You can help this project in the following way:
- ⭐ Put the star.
- 💡 Suggest your ideas.
- 😉 Open a founded issue.

## 📄 License

Default Values is MIT licensed, as found in the [LICENSE] file.
