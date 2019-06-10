# `codeceptjs-saucelabs`

> Run tests on Single or Multibrowsers in Parallel on Saucelabs

## Saucelabs: Single or Multibrowsers in Parallel

This module uses WebDriverIO `wdio` to run tests on single/multi-browsers tests parallel on saucelabs.

## Install

```bash
    npm i codeceptjs-saucelabs --save-dev
```

## Usage

In `codeceptjs.conf.js`,

1. Require following

```bash
    let merge = require('deepmerge');
    let sauce = require('codeceptjs-saucelabs');
```

2. Deep Merge and export your **Config** 

```bash
   exports.config = merge(<your_existing_codeceptjs_conf, sauce.conf);
```

## Run

**Important:** Make sure to export your Sauce Username and Sauce Access Key as env variables

```bash
    export SAUCE_USERNAME=<sauce_username>
    export SAUCE_KEY=<sauce_key>
```

It uses CodeceptJS `--profile` param to run tests on Saucelabs browsers as described below,

### Run on Single browser on Saucelabs

* command: `yarn acceptance`
* param: `--profile sauce:<sauce_browser>`
* available default browsers: `chrome`, `ie`, `edge`, `safari`, `firefox`

```bash
    yarn acceptance --grep @search_results --profile sauce:chrome
```

### Run Parallel on Multibrowsers on Saucelabs

* command: `yarn acceptance:multibrowsers`
* param: `--profile sauce:<first_sauce_browser>,<second_sauce_browser>,<and_so_on>`
* available default browsers: `chrome`, `ie`, `edge`, `safari`, `firefox`

```bash
    yarn acceptance:multibrowsers --grep @search_results --profile sauce:chrome,ie
```