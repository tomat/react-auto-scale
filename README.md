React Auto Scale
=========================

Wrap a single child with this component to make it auto-scale (`transform`) to fit its parent (or a maximum size specified through props).

## Installation

Requires **React 0.14 or later.** Currently uses [element-resize-event](https://github.com/KyleAMathews/element-resize-event) to detect resizing of elements without polling.

```
npm install --save react-auto-scale
```

This assumes that you’re using [npm](http://npmjs.com/) package manager with a module bundler like [Webpack](http://webpack.github.io) or [Browserify](http://browserify.org/) to consume [CommonJS modules](http://webpack.github.io/docs/commonjs.html).

## Usage

### Simple

`.myContent` will scale to fit inside `.myContainer`.

```javascript
import React, { Component } from 'react';
import AutoScale from 'react-auto-scale';

export default class MyComponent extends Component {
  render() {
    return (
      <div className="myContainer">
        <AutoScale>
          <div className="myContent">Example</div>
        </AutoScale>
      </div>
    );
  }
}
```

### A tiny bit less simple

`.myContent` will scale to fit inside `.myContainer`, but will at most grow to 400 px high, or 800 px wide, or at most 3x its original size.

```javascript
import React, { Component } from 'react';
import AutoScale from 'react-auto-scale';

export default class MyComponent extends Component {
  render() {
    return (
      <div className="myContainer">
        <AutoScale maxWidth={800} maxHeight={400} maxScale={3}>
          <div className="myContent">Example</div>
        </AutoScale>
      </div>
    );
  }
}
```

### Props

| Prop | Default | Description |
| --- | --- | --- |
| `maxHeight` | `null` | Number of pixels. Restrict the scale so that the content is at most this high. |
| `maxWidth` | `null` | Number of pixels. Restrict the scale so that the content is at most this wide. |
| `maxScale` | `null` | Don't scale beyond this number, i e `2` will scale at most 2x the original size. |
| `wrapperClass` | `""` | Class of the wrapper element, the outermost `div` that wraps the content. |
| `containerClass` | `""` | Class of the container element, the next outermost `div` that wraps the content. |
| `contentClass` | `""` | Class of the content element, the `div` that contains the content. |

## Support

This software is provided "as is", without warranty or support of any kind, express or implied. See [license](https://github.com/tomat/react-auto-scale/blob/master/LICENSE.md) for details.

## License

[MIT](https://github.com/tomat/react-auto-scale/blob/master/LICENSE.md)
