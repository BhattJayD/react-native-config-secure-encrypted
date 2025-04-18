<div align="center">

![react-native-config-encrypted](https://www.simplilearn.com/ice9/free_resources_article_thumb/React_Native_Tutorial.jpg)

[![Version](https://img.shields.io/npm/v/react-native-config-secure-encrypted)](https://www.npmjs.com/package/react-native-config-secure-encrypted)
[![Build](https://travis-ci.org/react-native-nation/react-native-config-encrypted.svg?branch=master)](https://travis-ci.org/react-native-nation/react-native-config-encrypted)
[![Coverage](https://coveralls.io/repos/github/react-native-nation/react-native-config-encrypted/badge.svg?branch=master)](https://coveralls.io/github/react-native-nation/react-native-config-encrypted?branch=master)
[![Minified size](https://img.shields.io/bundlephobia/min/react-native-config-encrypted)](https://github.com/react-native-nation/react-native-config-encrypted/blob/master/LICENSE)
[![Downloads](https://img.shields.io/npm/dm/react-native-config-secure-encrypted)](https://www.npmjs.com/package/react-native-config-secure-encrypted)
[![Dependabot](https://api.dependabot.com/badges/status?host=github&repo=react-native-nation/react-native-config-encrypted)](https://dependabot.com)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/react-native-nation/react-native-config-encrypted/pulls)
[![Tested with jest](https://img.shields.io/badge/tested_with-jest-99424f.svg)](https://github.com/facebook/jest)

</div>

# React Native Config Secure Encrypted

> ⚠️ This is a secure, maintained fork of `react-native-config-encrypted`, with `crypto-js` upgraded to `^4.2.0` to patch known vulnerabilities (CVE-2023-46233, CVE-2020-36732).

This package is a wrapper to encrypt the variables used by the `react-native-config`.

## Table of contents

- [How to install](#howtoinstall)
- [Encrypting env variables](#encrypting)
- [API Methods](#using)
- [Example](#example)
- [Community profile](#community)
- [Contributing](#contributing)

<a name="howtoinstall"></a>

## How to install

`react-native-config` is hard dependency, and must be installed.

```bash
yarn add react-native-config
```

then install the secure encrypted config wrapper:

```bash
yarn add react-native-config-secure-encrypted
```

<a name="encrypting"></a>

## Encrypting env variables

Usage: `example node_modules/.bin/env-config-encrypt <filename> <key> <property>`

```bash
node_modules/.bin/env-config-encrypt .env ^#$%Gg345@$@$ API_KEY_SECRET
```

then you can edit your environment variable

```
.env
API_KEY_SECRET="U2FsdGVkX1+FQEJRNuw8LAIKWQpVRd2Q0UAzJOspgI0fy0zLftyBNi0PdLJfaG1h"
```

<a name="using"></a>

## API Methods

# Get

To access to encrypted variables use the method `get`

```js
Config.get(propertyName, decrypt);
```

# Config

To configure the seed key use `configure`.

```js
import ConfigProvider from "react-native-config";

Config.configure({
  key: "your key",
  provider: ConfigProvider,
});
```

<a name="example"></a>

## Example

React native example

```js
import Config from "react-native-config-secure-encrypted";
import ConfigProvider from "react-native-config";

// Configure your library to use the seed key
Config.configure({
  key: "mysuperkey^$#123123ASDASD",
  provider: ConfigProvider,
});

// Get the env property
Config.get("API_KEY_SECRET");

// Get the raw env property
Config.get("API_KEY_SECRET", false);
```

<a name="community"></a>

## Community profile

Please read through our [CODE_OF_CONDUCT.md](/.github/CODE_OF_CONDUCT.md).

<a name="contributing"></a>

## Contributing

Please read through our [CONTRIBUTING.md](/.github/CONTRIBUTING.md).

<a name="reactnativenation"></a>

## React Native Nation

React Native Nation is the best spanish website for react native documentation.
[react-native-nation](https://reactnativenation.com).
