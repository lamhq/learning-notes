# Configure

## Extending Storybook’s webpack config

To extend the above configuration, use the `webpackFinal` field of `.storybook/main.js`.

```js
// .storybook/main.js

const path = require('path');

// Export a function. Accept the base config as the only param.
module.exports = {
  webpackFinal: async (config, { configType }) => {
    // `configType` has a value of 'DEVELOPMENT' or 'PRODUCTION'
    // You can change the configuration based on that.
    // 'PRODUCTION' is used when building the static version of storybook.

    // Make whatever fine-grained changes you need
    config.module.rules.push({
      test: /\.scss$/,
      use: ['style-loader', 'css-loader', 'sass-loader'],
      include: path.resolve(__dirname, '../'),
    });

    // Return the altered config
    return config;
  },
};
```

### Using your existing config

```js
// .storybook/main.js

const path = require('path');

// your app's webpack.config.js
const custom = require('../webpack.config.js');

module.exports = {
  webpackFinal: (config) => {
    return { ...config, module: { ...config.module, rules: custom.module.rules } };
  },
};
```