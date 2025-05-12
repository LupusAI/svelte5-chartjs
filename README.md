# svelte5-chartjs

<img align="right" width="150" height="150" alt="svelte-chartjs logo" src="https://raw.githubusercontent.com/SauravKanchan/svelte-chartjs/master/assets/svelte-chartjs.png">

Svelte 5 wrapper for [chart.js](https://www.chartjs.org/) Open for PRs and contributions!

> This is a fork of the [svelte-chartjs](https://github.com/SauravKanchan/svelte-chartjs) repo, which has been inactive for some time.


[![npm version](https://badge.fury.io/js/svelte-chartjs.svg)](https://badge.fury.io/js/svelte-chartjs)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FSauravKanchan%2Fsvelte-chartjs.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2FSauravKanchan%2Fsvelte-chartjs?ref=badge_shield)
![npm](https://img.shields.io/npm/dm/svelte-chartjs)

<br />
<a href="#install">Install</a>
<span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
<a href="#usage">Usage</a>
<span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
<a href="#migration-from-v1-to-v2">Migration guide</a>
<span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
<a href="#examples">Examples</a>
<span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
<a href="https://slack.cube.dev/?ref=eco-svelte-chartjs">Slack</a>
<span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
<a href="https://stackoverflow.com/questions/tagged/svelte-chartjs">Stack Overflow</a>
<br />
<hr />

## Install

Install this library with peer dependencies:

```bash
pnpm add svelte5-chartjs chart.js
# or
yarn add svelte5-chartjs chart.js
# or
npm i svelte5-chartjs chart.js
```

<hr />

Need an API to fetch data? Consider [Cube](https://cube.dev/?ref=eco-svelte-chartjs), an open-source API for data apps.

<br />

[![supported by Cube](https://user-images.githubusercontent.com/986756/154330861-d79ab8ec-aacb-4af8-9e17-1b28f1eccb01.svg)](https://cube.dev/?ref=eco-svelte-chartjs)

## Usage

```svelte
<script>
  import { Line } from 'svelte5-chartjs'
</script>

<Line data={...} />
```

### Custom Size

In order for Chart.js to obey the custom size you need to set `maintainAspectRatio` to false, example:

```svelte
<Line
  data={data}
  width={100}
  height={50}
  options={{ maintainAspectRatio: false }}
/>
```

### Tree-shaking

This library is tree-shakable [just like Chart.js v3](https://www.chartjs.org/docs/latest/getting-started/v3-migration.html#setup-and-installation). It means that you need to import and register the controllers, elements, scales, and plugins you want to use.

For a list of all the available items to import, see [Chart.js docs](https://www.chartjs.org/docs/latest/getting-started/integration.html#bundlers-webpack-rollup-etc).

```javascript
import { Line } from 'svelte5-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, LineElement, LinearScale, PointElement, CategoryScale } from 'chart.js';

ChartJS.register(Title, Tooltip, Legend, LineElement, LinearScale, PointElement, CategoryScale);
```

Please note that typed chart components register their controllers by default, so you don't need to register them by yourself. For example, when using the Pie component, you don't need to register PieController explicitly.

```javascript
import { Pie } from 'svelte5-chartjs';
import { Chart as ChartJS, Title, Tooltip, Legend, ArcElement, CategoryScale } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, ArcElement, CategoryScale)
```

## Examples

- [Bar Chart](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/bar)
- [Bubble Chart](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/bubble)
- [Doughnut Chart](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/doughnut)
- [Line Chart](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/line)
- [Pie Chart](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/pie)
- [PolarArea Chart](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/polar)
- [Radar Chart](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/radar)
- [Scatter Chart](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/scatter)
- [ChartJS instance](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/ref)
- [Events handling](https://codesandbox.io/s/github/SauravKanchan/svelte-chartjs/tree/master/sandboxes/events)

## Docs for v1

Full Documentation and demo for v1 [here](https://saurav.tech/mdbsvelte/?path=/story/charts--installation)
## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FSauravKanchan%2Fsvelte-chartjs.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2FSauravKanchan%2Fsvelte-chartjs?ref=badge_large)
