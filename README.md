## superset-plugin-chart-liquid

This plugin provides an example chart plugin for Superset to visualize percentages. The plugin has been built using the [Superset Yeoman Generator](https://www.npmjs.com/package/@superset-ui/generator-superset) and leverages the [And Design Charts](https://charts.ant.design) charting library.

![Liquid chart plugin in Explore view](https://raw.githubusercontent.com/preset-io/superset-plugin-chart-liquid/master/images/liquid.gif)

Preview in the chart picker

![Liquid chart plugin in Chart Picker](https://raw.githubusercontent.com/preset-io/superset-plugin-chart-liquid/master/images/liquid-picker.png)

### Usage

To build the plugin, run the following commands:

```
npm ci
npm run build
```

To run the plugin in development mode (=rebuilding whenever changes are made), start the dev server with the following command:

```
npm run dev
```

To add the package to Superset, go to the `superset-frontend` subdirectory in your Superset source folder (assuming both the `superset-plugin-chart-liquid` plugin and `superset` repos are in the same root directory) and run
```
npm i -S ../../superset-plugin-chart-liquid
```

or directly from npm by running
```
npm i -S superset-plugin-chart-liquid
```

After this edit the `superset-frontend/src/visualizations/presets/MainPreset.js` and make the following changes:

```js
import { LiquidChartPlugin } from 'superset-plugin-chart-liquid';
```

to import the plugin and later add the following to the array that's passed to the `plugins` property:
```js
new LiquidChartPlugin().configure({ key: 'liquid' }),
```

After that the plugin should show up when you run Superset, e.g. the development server:

```
npm run dev-server
```
