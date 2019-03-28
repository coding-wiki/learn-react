# Learn React


## Introduction

To display or manipulate content in a browser, we need to interact with the DOM; however, using vanilla JavaScript and HTML does not scale very well for web apps.

DOM operations are expensive, so React.js introduces the concept of a Virtual DOM. An API is provided with a series of abstractions that give us a declarative system to write modular component with, where React will perform DOM updates in a more performant way by checking diffs.

## HTML Entry Point

Everything starts with an entry-point in HTML which acts as a "sandbox" for React to operate inside of. You can think of it as a sort of `iframe`.

**`<div id="root">` is our entry point:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    ...
  </head>
  <body>
    <div id="root">
      
    </div>
    <script src="bundled-script-here.min.js" />
  </body>
</html>
```

We can interact with this container element in JavaScript with `document.getElemenyById('root')`, which will give us a reference to its DOM object.

## ReactDOM

React can render to a number of platforms. While it is primarly used for web, React components can have native bindings to  mobile platforms, VR platforms, Sketch, etc through a JavaScript bridge.

To render to web, we need the package `react-dom`.


**index.js**

```js
import ReactDOM from 'react-dom';

const root = document.getElementById('root');

ReactDOM.render(App, root);
```

Next, we need `App`, which is a component. If all you need is a single page, one component may be enough, but eventually, you'll need to split your code up into separate components, which may be reused across different components.

This is great for having separation of concerns and improving readability.

**create App.js:**

```js
import React, { createElement } from 'react';

const e = createElement;

/* Where e creates a component
 * - { } is a placeholder, which can be populated with props (directional data flow)
 * - 'Hello World' is a children prop (rendered to the virtual DOM, so is user-facing UI)
const App = e(
  'p',
  {},
  'Hello World'
);
```

Now you can import `App.js` in your JavaScript entry point file (`index.js` to complete it).

**index.js**

```js
import App from './App.jsx';
```
