React Auto Scale
=========================

Wrap a single child with this component to make it auto-scale to fit its parent (or a maximum size specified through props).

Scaling is done using a CSS `transform`.

## Installation

Requires **React 0.14 or later.**

```
npm install --save react-auto-scale
```

This assumes that you’re using [npm](http://npmjs.com/) package manager with a module bundler like [Webpack](http://webpack.github.io) or [Browserify](http://browserify.org/) to consume [CommonJS modules](http://webpack.github.io/docs/commonjs.html).

## Usage

### Simple

`.myContent` will scale to fit inside `.myContainer`.

```javascript
import React, { PropTypes, Component } from 'react';
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
import React, { PropTypes, Component } from 'react';
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

## Support

This software is provided "as is", without warranty or support of any kind, express or implied. See [license](https://github.com/tomat/react-reflorp/blob/master/LICENSE.md) for details.

## License

[MIT](https://github.com/tomat/react-auto-scale/blob/master/LICENSE.md)
