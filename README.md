# next-nipple

A next.js wrapper for the [nipplejs](https://www.npmjs.com/package/nipplejs) on-screen-joystick.

<img src="https://raw.githubusercontent.com/loopmode/react-nipple/master/packages/react-nipple/preview.gif" />

### Resources

-   Github repository: []()
-   NPM package: [https://www.npmjs.com/package/next-nipple](https://www.npmjs.com/package/next-nipple)
-   Docs: [https://loopmode.github.io/react-nipple/](https://loopmode.github.io/react-nipple/)

## Installation

```bash
yarn add next-nipple
# or using npm:
npm install --save next-nipple
```

## Usage

Import and use the component. It supports all `options` from `nipplejs`.  
It provides callbacks for all supported event types in a camel-cased `on`-notation, e.g. `start` -> `onStart`.

```javascript
import React from 'react';
import NextNipple from 'next-nipple';

// optional: include the stylesheet somewhere in your app
import 'next-nipple/lib/styles.css';

class Example extends React.Component {
    render() {
        return (
            <div>
                <NextNipple
                    // supports all nipplejs options
                    // see https://github.com/yoannmoinet/nipplejs#options
                    options={{ mode: 'static', position: { top: '50%', left: '50%' } }}
                    // any unknown props will be passed to the container element, e.g. 'title', 'style' etc
                    style={{
                        outline: '1px dashed red',
                        width: 150,
                        height: 150
                        // if you pass position: 'relative', you don't need to import the stylesheet
                    }}
                    // all events supported by nipplejs are available as callbacks
                    // see https://github.com/yoannmoinet/nipplejs#start
                    onMove={(evt, data) => console.log(evt, data)}
                />
            </div>
        );
    }
}
```

### Additional features

-   There is an additional `onCreated` callback that receives the created `nipplejs` instance - you might want to use it for direct access to instance methods etc.
-   You can pass the boolean `static` flag as a prop, which is a shortcut for `options={{mode: 'static', position: {top: '50%', let: '50%'}}}`

