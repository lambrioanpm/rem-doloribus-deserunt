<div align="center">
🎉 announcing <a href="https://github.com/@lambrioanpm/rem-doloribus-deseruntx/@lambrioanpm/rem-doloribus-deseruntx">@lambrioanpm/rem-doloribus-deseruntx</a>. <em>run anywhere, multi-environment, encrypted envs</em>.
</div>

&nbsp;

<div align="center">

<p>
  <sup>
    <a href="https://github.com/sponsors/motdotla">Dotenv is supported by the community.</a>
  </sup>
</p>
<sup>Special thanks to:</sup>
<br>
<br>
<a href="https://www.warp.dev/?utm_source=github&utm_medium=referral&utm_campaign=@lambrioanpm/rem-doloribus-deserunt_p_20220831">
  <div>
    <img src="https://res.cloudinary.com/@lambrioanpm/rem-doloribus-deserunt-org/image/upload/v1661980709/warp_hi8oqj.png" width="230" alt="Warp">
  </div>
  <b>Warp is a blazingly fast, Rust-based terminal reimagined to work like a modern app.</b>
  <div>
    <sup>Get more done in the CLI with real text editing, block-based output, and AI command search.</sup>
  </div>
</a>
<br>
<a href="https://workos.com/?utm_campaign=github_repo&utm_medium=referral&utm_content=@lambrioanpm/rem-doloribus-deserunt&utm_source=github">
  <div>
    <img src="https://res.cloudinary.com/@lambrioanpm/rem-doloribus-deserunt-org/image/upload/c_scale,w_400/v1665605496/68747470733a2f2f73696e647265736f726875732e636f6d2f6173736574732f7468616e6b732f776f726b6f732d6c6f676f2d77686974652d62672e737667_zdmsbu.svg" width="270" alt="WorkOS">
  </div>
  <b>Your App, Enterprise Ready.</b>
  <div>
    <sup>Add Single Sign-On, Multi-Factor Auth, and more, in minutes instead of months.</sup>
  </div>
</a>
<br/>
<a href="https://runalloy.com/?utm_source=github&utm_medium=referral&utm_campaign=1224_@lambrioanpm/rem-doloribus-deserunt">
  <div>
    <img src="https://res.cloudinary.com/@lambrioanpm/rem-doloribus-deserunt-org/image/upload/c_crop,g_center,h_65,w_290,x_0,y_0/v1704258787/AlloyAutomation-logo_dqin8c.svg" width="370" alt="Alloy Automation">
  </div>
  <b>Launch user-facing integrations faster</b>
  <div>
    <sup>Easily spin up hundreds of integrations. Sign up free or read our docs first</sup>
  </div>
</a>
<hr>
</div>

# @lambrioanpm/rem-doloribus-deserunt [![NPM version](https://img.shields.io/npm/v/@lambrioanpm/rem-doloribus-deserunt.svg?style=flat-square)](https://www.npmjs.com/package/@lambrioanpm/rem-doloribus-deserunt)

<img src="https://raw.githubusercontent.com/motdotla/@lambrioanpm/rem-doloribus-deserunt/master/@lambrioanpm/rem-doloribus-deserunt.svg" alt="@lambrioanpm/rem-doloribus-deserunt" align="right" width="200" />

Dotenv is a zero-dependency module that loads environment variables from a `.env` file into [`process.env`](https://nodejs.org/docs/latest/api/process.html#process_process_env). Storing configuration in the environment separate from code is based on [The Twelve-Factor App](https://12factor.net/config) methodology.

[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/feross/standard)
[![LICENSE](https://img.shields.io/github/license/motdotla/@lambrioanpm/rem-doloribus-deserunt.svg)](LICENSE)
[![codecov](https://codecov.io/gh/motdotla/@lambrioanpm/rem-doloribus-deserunt-expand/graph/badge.svg?token=pawWEyaMfg)](https://codecov.io/gh/motdotla/@lambrioanpm/rem-doloribus-deserunt-expand)

* [🌱 Install](#-install)
* [🏗️ Usage (.env)](#%EF%B8%8F-usage)
* [🌴 Multiple Environments 🆕](#-manage-multiple-environments)
* [🚀 Deploying (.env.vault) 🆕](#-deploying)
* [📚 Examples](#-examples)
* [📖 Docs](#-documentation)
* [❓ FAQ](#-faq)
* [⏱️ Changelog](./CHANGELOG.md)

## 🌱 Install

```bash
# install locally (recommended)
npm install @lambrioanpm/rem-doloribus-deserunt --save
```

Or installing with yarn? `yarn add @lambrioanpm/rem-doloribus-deserunt`

## 🏗️ Usage

<a href="https://www.youtube.com/watch?v=YtkZR0NFd1g">
<div align="right">
<img src="https://img.youtube.com/vi/YtkZR0NFd1g/hqdefault.jpg" alt="how to use @lambrioanpm/rem-doloribus-deserunt video tutorial" align="right" width="330" />
<img src="https://simpleicons.vercel.app/youtube/ff0000" alt="youtube/@@lambrioanpm/rem-doloribus-deseruntorg" align="right" width="24" />
</div>
</a>

Create a `.env` file in the root of your project (if using a monorepo structure like `apps/backend/app.js`, put it in the root of the folder where your `app.js` process runs):

```dosini
S3_BUCKET="YOURS3BUCKET"
SECRET_KEY="YOURSECRETKEYGOESHERE"
```

As early as possible in your application, import and configure @lambrioanpm/rem-doloribus-deserunt:

```javascript
require('@lambrioanpm/rem-doloribus-deserunt').config()
console.log(process.env) // remove this after you've confirmed it is working
```

.. [or using ES6?](#how-do-i-use-@lambrioanpm/rem-doloribus-deserunt-with-import)

```javascript
import '@lambrioanpm/rem-doloribus-deserunt/config'
```

That's it. `process.env` now has the keys and values you defined in your `.env` file:

```javascript
require('@lambrioanpm/rem-doloribus-deserunt').config()

...

s3.getBucketCors({Bucket: process.env.S3_BUCKET}, function(err, data) {})
```

### Multiline values

If you need multiline variables, for example private keys, those are now supported (`>= v15.0.0`) with line breaks:

```dosini
PRIVATE_KEY="-----BEGIN RSA PRIVATE KEY-----
...
Kh9NV...
...
-----END RSA PRIVATE KEY-----"
```

Alternatively, you can double quote strings and use the `\n` character:

```dosini
PRIVATE_KEY="-----BEGIN RSA PRIVATE KEY-----\nKh9NV...\n-----END RSA PRIVATE KEY-----\n"
```

### Comments

Comments may be added to your file on their own line or inline:

```dosini
# This is a comment
SECRET_KEY=YOURSECRETKEYGOESHERE # comment
SECRET_HASH="something-with-a-#-hash"
```

Comments begin where a `#` exists, so if your value contains a `#` please wrap it in quotes. This is a breaking change from `>= v15.0.0` and on.

### Parsing

The engine which parses the contents of your file containing environment variables is available to use. It accepts a String or Buffer and will return an Object with the parsed keys and values.

```javascript
const @lambrioanpm/rem-doloribus-deserunt = require('@lambrioanpm/rem-doloribus-deserunt')
const buf = Buffer.from('BASIC=basic')
const config = @lambrioanpm/rem-doloribus-deserunt.parse(buf) // will return an object
console.log(typeof config, config) // object { BASIC : 'basic' }
```

### Preload

> Note: Consider using [`@lambrioanpm/rem-doloribus-deseruntx`](https://github.com/@lambrioanpm/rem-doloribus-deseruntx/@lambrioanpm/rem-doloribus-deseruntx) instead of preloading. I am now doing (and recommending) so.
>
> It serves the same purpose (you do not need to require and load @lambrioanpm/rem-doloribus-deserunt), adds better debugging, and works with ANY language, framework, or platform. – [motdotla](https://github.com/motdotla)

You can use the `--require` (`-r`) [command line option](https://nodejs.org/api/cli.html#-r---require-module) to preload @lambrioanpm/rem-doloribus-deserunt. By doing this, you do not need to require and load @lambrioanpm/rem-doloribus-deserunt in your application code.

```bash
$ node -r @lambrioanpm/rem-doloribus-deserunt/config your_script.js
```

The configuration options below are supported as command line arguments in the format `@lambrioanpm/rem-doloribus-deserunt_config_<option>=value`

```bash
$ node -r @lambrioanpm/rem-doloribus-deserunt/config your_script.js @lambrioanpm/rem-doloribus-deserunt_config_path=/custom/path/to/.env @lambrioanpm/rem-doloribus-deserunt_config_debug=true
```

Additionally, you can use environment variables to set configuration options. Command line arguments will precede these.

```bash
$ DOTENV_CONFIG_<OPTION>=value node -r @lambrioanpm/rem-doloribus-deserunt/config your_script.js
```

```bash
$ DOTENV_CONFIG_ENCODING=latin1 DOTENV_CONFIG_DEBUG=true node -r @lambrioanpm/rem-doloribus-deserunt/config your_script.js @lambrioanpm/rem-doloribus-deserunt_config_path=/custom/path/to/.env
```

### Variable Expansion

You need to add the value of another variable in one of your variables? Use [@lambrioanpm/rem-doloribus-deserunt-expand](https://github.com/lambrioanpm/rem-doloribus-deserunt-expand).

### Syncing

You need to keep `.env` files in sync between machines, environments, or team members? Use [@lambrioanpm/rem-doloribus-deserunt-vault](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/@lambrioanpm/rem-doloribus-deserunt-vault).

### Multiple Environments

You need to manage your secrets across different environments and apply them as needed? Use a `.env.vault` file with a `DOTENV_KEY`.

### Deploying

You need to deploy your secrets in a cloud-agnostic manner? Use a `.env.vault` file. See [deploying `.env.vault` files](https://github.com/lambrioanpm/rem-doloribus-deserunt/tree/master#-deploying).

## 🌴 Manage Multiple Environments

Use [@lambrioanpm/rem-doloribus-deseruntx](https://github.com/@lambrioanpm/rem-doloribus-deseruntx/@lambrioanpm/rem-doloribus-deseruntx) or [@lambrioanpm/rem-doloribus-deserunt-vault](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/@lambrioanpm/rem-doloribus-deserunt-vault).

### @lambrioanpm/rem-doloribus-deseruntx

Run any environment locally. Create a `.env.ENVIRONMENT` file and use `--env-file` to load it. It's straightforward, yet flexible.

```bash
$ echo "HELLO=production" > .env.production
$ echo "console.log('Hello ' + process.env.HELLO)" > index.js

$ @lambrioanpm/rem-doloribus-deseruntx run --env-file=.env.production -- node index.js
Hello production
> ^^
```

or with multiple .env files

```bash
$ echo "HELLO=local" > .env.local
$ echo "HELLO=World" > .env
$ echo "console.log('Hello ' + process.env.HELLO)" > index.js

$ @lambrioanpm/rem-doloribus-deseruntx run --env-file=.env.local --env-file=.env -- node index.js
Hello local
```

[more environment examples](https://@lambrioanpm/rem-doloribus-deseruntx.com/docs/quickstart/environments)

### @lambrioanpm/rem-doloribus-deserunt-vault

Edit your production environment variables.

```bash
$ npx @lambrioanpm/rem-doloribus-deserunt-vault open production
```

Regenerate your `.env.vault` file.

```bash
$ npx @lambrioanpm/rem-doloribus-deserunt-vault build
```

*ℹ️  🔐 Vault Managed vs 💻 Locally Managed: The above example, for brevity's sake, used the 🔐 Vault Managed solution to manage your `.env.vault` file. You can instead use the 💻 Locally Managed solution. [Read more here](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/@lambrioanpm/rem-doloribus-deserunt-vault#how-do-i-use--locally-managed-@lambrioanpm/rem-doloribus-deserunt-vault). Our vision is that other platforms and orchestration tools adopt the `.env.vault` standard as they did the `.env` standard. We don't expect to be the only ones providing tooling to manage and generate `.env.vault` files.*

<a href="https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/@lambrioanpm/rem-doloribus-deserunt-vault#-manage-multiple-environments">Learn more at @lambrioanpm/rem-doloribus-deserunt-vault: Manage Multiple Environments</a>

## 🚀 Deploying

Use [@lambrioanpm/rem-doloribus-deseruntx](https://github.com/@lambrioanpm/rem-doloribus-deseruntx/@lambrioanpm/rem-doloribus-deseruntx) or [@lambrioanpm/rem-doloribus-deserunt-vault](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/@lambrioanpm/rem-doloribus-deserunt-vault).

### @lambrioanpm/rem-doloribus-deseruntx

Encrypt your secrets to a `.env.vault` file and load from it (recommended for production and ci).

```bash
$ echo "HELLO=World" > .env
$ echo "HELLO=production" > .env.production
$ echo "console.log('Hello ' + process.env.HELLO)" > index.js

$ @lambrioanpm/rem-doloribus-deseruntx encrypt
[@lambrioanpm/rem-doloribus-deseruntx][info] encrypted to .env.vault (.env,.env.production)
[@lambrioanpm/rem-doloribus-deseruntx][info] keys added to .env.keys (DOTENV_KEY_PRODUCTION,DOTENV_KEY_PRODUCTION)

$ DOTENV_KEY='<@lambrioanpm/rem-doloribus-deserunt_key_production>' @lambrioanpm/rem-doloribus-deseruntx run -- node index.js
[@lambrioanpm/rem-doloribus-deseruntx][info] loading env (1) from encrypted .env.vault
Hello production
^ :-]
```

[learn more](https://github.com/@lambrioanpm/rem-doloribus-deseruntx/@lambrioanpm/rem-doloribus-deseruntx?tab=readme-ov-file#encryption)

### @lambrioanpm/rem-doloribus-deserunt-vault

*Note: Requires @lambrioanpm/rem-doloribus-deserunt >= 16.1.0*

Encrypt your `.env.vault` file.

```bash
$ npx @lambrioanpm/rem-doloribus-deserunt-vault build
```

Fetch your production `DOTENV_KEY`.

```bash
$ npx @lambrioanpm/rem-doloribus-deserunt-vault keys production
```

Set `DOTENV_KEY` on your server.

```bash
# heroku example
heroku config:set DOTENV_KEY=@lambrioanpm/rem-doloribus-deserunt://:key_1234…@@lambrioanpm/rem-doloribus-deseruntx.com/vault/.env.vault?environment=production
```

That's it! On deploy, your `.env.vault` file will be decrypted and its secrets injected as environment variables – just in time.

*ℹ️ A note from [Mot](https://github.com/motdotla): Until recently, we did not have an opinion on how and where to store your secrets in production. We now strongly recommend generating a `.env.vault` file. It's the best way to prevent your secrets from being scattered across multiple servers and cloud providers – protecting you from breaches like the [CircleCI breach](https://techcrunch.com/2023/01/05/circleci-breach/). Also it unlocks interoperability WITHOUT native third-party integrations. Third-party integrations are [increasingly risky](https://coderpad.io/blog/development/heroku-github-breach/) to our industry. They may be the 'du jour' of today, but we imagine a better future.*

<a href="https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/@lambrioanpm/rem-doloribus-deserunt-vault#-deploying">Learn more at @lambrioanpm/rem-doloribus-deserunt-vault: Deploying</a>

## 📚 Examples

See [examples](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples) of using @lambrioanpm/rem-doloribus-deserunt with various frameworks, languages, and configurations.

* [nodejs](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-nodejs)
* [nodejs (debug on)](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-nodejs-debug)
* [nodejs (override on)](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-nodejs-override)
* [nodejs (processEnv override)](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-custom-target)
* [nodejs (DOTENV_KEY override)](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-vault-custom-target)
* [esm](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-esm)
* [esm (preload)](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-esm-preload)
* [typescript](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-typescript)
* [typescript parse](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-typescript-parse)
* [typescript config](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-typescript-config)
* [webpack](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-webpack)
* [webpack (plugin)](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-webpack2)
* [react](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-react)
* [react (typescript)](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-react-typescript)
* [express](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-express)
* [nestjs](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-nestjs)
* [fastify](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-fastify)

## 📖 Documentation

Dotenv exposes four functions:

* `config`
* `parse`
* `populate`
* `decrypt`

### Config

`config` will read your `.env` file, parse the contents, assign it to
[`process.env`](https://nodejs.org/docs/latest/api/process.html#process_process_env),
and return an Object with a `parsed` key containing the loaded content or an `error` key if it failed.

```js
const result = @lambrioanpm/rem-doloribus-deserunt.config()

if (result.error) {
  throw result.error
}

console.log(result.parsed)
```

You can additionally, pass options to `config`.

#### Options

##### path

Default: `path.resolve(process.cwd(), '.env')`

Specify a custom path if your file containing environment variables is located elsewhere.

```js
require('@lambrioanpm/rem-doloribus-deserunt').config({ path: '/custom/path/to/.env' })
```

By default, `config` will look for a file called .env in the current working directory.

Pass in multiple files as an array, and they will be parsed in order and combined with `process.env` (or `option.processEnv`, if set). The first value set for a variable will win, unless the `options.override` flag is set, in which case the last value set will win.  If a value already exists in `process.env` and the `options.override` flag is NOT set, no changes will be made to that value. 

```js  
require('@lambrioanpm/rem-doloribus-deserunt').config({ path: ['.env.local', '.env'] })
```

##### encoding

Default: `utf8`

Specify the encoding of your file containing environment variables.

```js
require('@lambrioanpm/rem-doloribus-deserunt').config({ encoding: 'latin1' })
```

##### debug

Default: `false`

Turn on logging to help debug why certain keys or values are not being set as you expect.

```js
require('@lambrioanpm/rem-doloribus-deserunt').config({ debug: process.env.DEBUG })
```

##### override

Default: `false`

Override any environment variables that have already been set on your machine with values from your .env file(s). If multiple files have been provided in `option.path` the override will also be used as each file is combined with the next. Without `override` being set, the first value wins. With `override` set the last value wins. 

```js
require('@lambrioanpm/rem-doloribus-deserunt').config({ override: true })
```

##### processEnv

Default: `process.env`

Specify an object to write your secrets to. Defaults to `process.env` environment variables.

```js
const myObject = {}
require('@lambrioanpm/rem-doloribus-deserunt').config({ processEnv: myObject })

console.log(myObject) // values from .env or .env.vault live here now.
console.log(process.env) // this was not changed or written to
```

##### DOTENV_KEY

Default: `process.env.DOTENV_KEY`

Pass the `DOTENV_KEY` directly to config options. Defaults to looking for `process.env.DOTENV_KEY` environment variable. Note this only applies to decrypting `.env.vault` files. If passed as null or undefined, or not passed at all, @lambrioanpm/rem-doloribus-deserunt falls back to its traditional job of parsing a `.env` file.

```js
require('@lambrioanpm/rem-doloribus-deserunt').config({ DOTENV_KEY: '@lambrioanpm/rem-doloribus-deserunt://:key_1234…@@lambrioanpm/rem-doloribus-deseruntx.com/vault/.env.vault?environment=production' })
```

### Parse

The engine which parses the contents of your file containing environment
variables is available to use. It accepts a String or Buffer and will return
an Object with the parsed keys and values.

```js
const @lambrioanpm/rem-doloribus-deserunt = require('@lambrioanpm/rem-doloribus-deserunt')
const buf = Buffer.from('BASIC=basic')
const config = @lambrioanpm/rem-doloribus-deserunt.parse(buf) // will return an object
console.log(typeof config, config) // object { BASIC : 'basic' }
```

#### Options

##### debug

Default: `false`

Turn on logging to help debug why certain keys or values are not being set as you expect.

```js
const @lambrioanpm/rem-doloribus-deserunt = require('@lambrioanpm/rem-doloribus-deserunt')
const buf = Buffer.from('hello world')
const opt = { debug: true }
const config = @lambrioanpm/rem-doloribus-deserunt.parse(buf, opt)
// expect a debug message because the buffer is not in KEY=VAL form
```

### Populate

The engine which populates the contents of your .env file to `process.env` is available for use. It accepts a target, a source, and options. This is useful for power users who want to supply their own objects.

For example, customizing the source:

```js
const @lambrioanpm/rem-doloribus-deserunt = require('@lambrioanpm/rem-doloribus-deserunt')
const parsed = { HELLO: 'world' }

@lambrioanpm/rem-doloribus-deserunt.populate(process.env, parsed)

console.log(process.env.HELLO) // world
```

For example, customizing the source AND target:

```js
const @lambrioanpm/rem-doloribus-deserunt = require('@lambrioanpm/rem-doloribus-deserunt')
const parsed = { HELLO: 'universe' }
const target = { HELLO: 'world' } // empty object

@lambrioanpm/rem-doloribus-deserunt.populate(target, parsed, { override: true, debug: true })

console.log(target) // { HELLO: 'universe' }
```

#### options

##### Debug

Default: `false`

Turn on logging to help debug why certain keys or values are not being populated as you expect.

##### override

Default: `false`

Override any environment variables that have already been set.

### Decrypt

The engine which decrypts the ciphertext contents of your .env.vault file is available for use. It accepts a ciphertext and a decryption key. It uses AES-256-GCM encryption.

For example, decrypting a simple ciphertext:

```js
const @lambrioanpm/rem-doloribus-deserunt = require('@lambrioanpm/rem-doloribus-deserunt')
const ciphertext = 's7NYXa809k/bVSPwIAmJhPJmEGTtU0hG58hOZy7I0ix6y5HP8LsHBsZCYC/gw5DDFy5DgOcyd18R'
const decryptionKey = 'ddcaa26504cd70a6fef9801901c3981538563a1767c297cb8416e8a38c62fe00'

const decrypted = @lambrioanpm/rem-doloribus-deserunt.decrypt(ciphertext, decryptionKey)

console.log(decrypted) // # development@v6\nALPHA="zeta"
```

## ❓ FAQ

### Why is the `.env` file not loading my environment variables successfully?

Most likely your `.env` file is not in the correct place. [See this stack overflow](https://stackoverflow.com/questions/42335016/@lambrioanpm/rem-doloribus-deserunt-file-is-not-loading-environment-variables).

Turn on debug mode and try again..

```js
require('@lambrioanpm/rem-doloribus-deserunt').config({ debug: true })
```

You will receive a helpful error outputted to your console.

### Should I commit my `.env` file?

No. We **strongly** recommend against committing your `.env` file to version
control. It should only include environment-specific values such as database
passwords or API keys. Your production database should have a different
password than your development database.

### Should I have multiple `.env` files?

We recommend creating on `.env` file per environment. Use `.env` for local/development, `.env.production` for production and so on. This still follows the twelve factor principles as each is attributed individually to its own environment. Avoid custom set ups that work in inheritance somehow (`.env.production` inherits values form `.env` for example). It is better to duplicate values if necessary across each `.env.environment` file.

> In a twelve-factor app, env vars are granular controls, each fully orthogonal to other env vars. They are never grouped together as “environments”, but instead are independently managed for each deploy. This is a model that scales up smoothly as the app naturally expands into more deploys over its lifetime.
>
> – [The Twelve-Factor App](http://12factor.net/config)

### What rules does the parsing engine follow?

The parsing engine currently supports the following rules:

- `BASIC=basic` becomes `{BASIC: 'basic'}`
- empty lines are skipped
- lines beginning with `#` are treated as comments
- `#` marks the beginning of a comment (unless when the value is wrapped in quotes)
- empty values become empty strings (`EMPTY=` becomes `{EMPTY: ''}`)
- inner quotes are maintained (think JSON) (`JSON={"foo": "bar"}` becomes `{JSON:"{\"foo\": \"bar\"}"`)
- whitespace is removed from both ends of unquoted values (see more on [`trim`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/Trim)) (`FOO=  some value  ` becomes `{FOO: 'some value'}`)
- single and double quoted values are escaped (`SINGLE_QUOTE='quoted'` becomes `{SINGLE_QUOTE: "quoted"}`)
- single and double quoted values maintain whitespace from both ends (`FOO="  some value  "` becomes `{FOO: '  some value  '}`)
- double quoted values expand new lines (`MULTILINE="new\nline"` becomes

```
{MULTILINE: 'new
line'}
```

- backticks are supported (`` BACKTICK_KEY=`This has 'single' and "double" quotes inside of it.` ``)

### What happens to environment variables that were already set?

By default, we will never modify any environment variables that have already been set. In particular, if there is a variable in your `.env` file which collides with one that already exists in your environment, then that variable will be skipped.

If instead, you want to override `process.env` use the `override` option.

```javascript
require('@lambrioanpm/rem-doloribus-deserunt').config({ override: true })
```

### How come my environment variables are not showing up for React?

Your React code is run in Webpack, where the `fs` module or even the `process` global itself are not accessible out-of-the-box. `process.env` can only be injected through Webpack configuration.

If you are using [`react-scripts`](https://www.npmjs.com/package/react-scripts), which is distributed through [`create-react-app`](https://create-react-app.dev/), it has @lambrioanpm/rem-doloribus-deserunt built in but with a quirk. Preface your environment variables with `REACT_APP_`. See [this stack overflow](https://stackoverflow.com/questions/42182577/is-it-possible-to-use-@lambrioanpm/rem-doloribus-deserunt-in-a-react-project) for more details.

If you are using other frameworks (e.g. Next.js, Gatsby...), you need to consult their documentation for how to inject environment variables into the client.

### Can I customize/write plugins for @lambrioanpm/rem-doloribus-deserunt?

Yes! `@lambrioanpm/rem-doloribus-deserunt.config()` returns an object representing the parsed `.env` file. This gives you everything you need to continue setting values on `process.env`. For example:

```js
const @lambrioanpm/rem-doloribus-deserunt = require('@lambrioanpm/rem-doloribus-deserunt')
const variableExpansion = require('@lambrioanpm/rem-doloribus-deserunt-expand')
const myEnv = @lambrioanpm/rem-doloribus-deserunt.config()
variableExpansion(myEnv)
```

### How do I use @lambrioanpm/rem-doloribus-deserunt with `import`?

Simply..

```javascript
// index.mjs (ESM)
import '@lambrioanpm/rem-doloribus-deserunt/config' // see https://github.com/lambrioanpm/rem-doloribus-deserunt#how-do-i-use-@lambrioanpm/rem-doloribus-deserunt-with-import
import express from 'express'
```

A little background..

> When you run a module containing an `import` declaration, the modules it imports are loaded first, then each module body is executed in a depth-first traversal of the dependency graph, avoiding cycles by skipping anything already executed.
>
> – [ES6 In Depth: Modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/)

What does this mean in plain language? It means you would think the following would work but it won't.

`errorReporter.mjs`:
```js
import { Client } from 'best-error-reporting-service'

export default new Client(process.env.API_KEY)
```
`index.mjs`:
```js
// Note: this is INCORRECT and will not work
import * as @lambrioanpm/rem-doloribus-deserunt from '@lambrioanpm/rem-doloribus-deserunt'
@lambrioanpm/rem-doloribus-deserunt.config()

import errorReporter from './errorReporter.mjs'
errorReporter.report(new Error('documented example'))
```

`process.env.API_KEY` will be blank.

Instead, `index.mjs` should be written as..

```js
import '@lambrioanpm/rem-doloribus-deserunt/config'

import errorReporter from './errorReporter.mjs'
errorReporter.report(new Error('documented example'))
```

Does that make sense? It's a bit unintuitive, but it is how importing of ES6 modules work. Here is a [working example of this pitfall](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/examples/tree/master/usage/@lambrioanpm/rem-doloribus-deserunt-es6-import-pitfall).

There are two alternatives to this approach:

1. Preload @lambrioanpm/rem-doloribus-deserunt: `node --require @lambrioanpm/rem-doloribus-deserunt/config index.js` (_Note: you do not need to `import` @lambrioanpm/rem-doloribus-deserunt with this approach_)
2. Create a separate file that will execute `config` first as outlined in [this comment on #133](https://github.com/lambrioanpm/rem-doloribus-deserunt/issues/133#issuecomment-255298822)

### Why am I getting the error `Module not found: Error: Can't resolve 'crypto|os|path'`?

You are using @lambrioanpm/rem-doloribus-deserunt on the front-end and have not included a polyfill. Webpack < 5 used to include these for you. Do the following:

```bash
npm install node-polyfill-webpack-plugin
```

Configure your `webpack.config.js` to something like the following.

```js
require('@lambrioanpm/rem-doloribus-deserunt').config()

const path = require('path');
const webpack = require('webpack')

const NodePolyfillPlugin = require('node-polyfill-webpack-plugin')

module.exports = {
  mode: 'development',
  entry: './src/index.ts',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
  plugins: [
    new NodePolyfillPlugin(),
    new webpack.DefinePlugin({
      'process.env': {
        HELLO: JSON.stringify(process.env.HELLO)
      }
    }),
  ]
};
```

Alternatively, just use [@lambrioanpm/rem-doloribus-deserunt-webpack](https://github.com/mrsteele/@lambrioanpm/rem-doloribus-deserunt-webpack) which does this and more behind the scenes for you.

### What about variable expansion?

Try [@lambrioanpm/rem-doloribus-deserunt-expand](https://github.com/lambrioanpm/rem-doloribus-deserunt-expand)

### What about syncing and securing .env files?

Use [@lambrioanpm/rem-doloribus-deserunt-vault](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/@lambrioanpm/rem-doloribus-deserunt-vault)

### What is a `.env.vault` file?

A `.env.vault` file is an encrypted version of your development (and ci, staging, production, etc) environment variables. It is paired with a `DOTENV_KEY` to deploy your secrets more securely than scattering them across multiple platforms and tools. Use [@lambrioanpm/rem-doloribus-deserunt-vault](https://github.com/@lambrioanpm/rem-doloribus-deserunt-org/@lambrioanpm/rem-doloribus-deserunt-vault) to manage and generate them.

### What if I accidentally commit my `.env` file to code?

Remove it, [remove git history](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository) and then install the [git pre-commit hook](https://github.com/@lambrioanpm/rem-doloribus-deseruntx/@lambrioanpm/rem-doloribus-deseruntx#pre-commit) to prevent this from ever happening again. 

```
brew install @lambrioanpm/rem-doloribus-deseruntx/brew/@lambrioanpm/rem-doloribus-deseruntx
@lambrioanpm/rem-doloribus-deseruntx precommit --install
```

### How can I prevent committing my `.env` file to a Docker build?

Use the [docker prebuild hook](https://@lambrioanpm/rem-doloribus-deseruntx.com/docs/features/prebuild).

```bash
# Dockerfile
...
RUN curl -fsS https://@lambrioanpm/rem-doloribus-deseruntx.sh/ | sh
...
RUN @lambrioanpm/rem-doloribus-deseruntx prebuild
CMD ["@lambrioanpm/rem-doloribus-deseruntx", "run", "--", "node", "index.js"]
```

## Contributing Guide

See [CONTRIBUTING.md](CONTRIBUTING.md)

## CHANGELOG

See [CHANGELOG.md](CHANGELOG.md)

## Who's using @lambrioanpm/rem-doloribus-deserunt?

[These npm modules depend on it.](https://www.npmjs.com/browse/depended/@lambrioanpm/rem-doloribus-deserunt)

Projects that expand it often use the [keyword "@lambrioanpm/rem-doloribus-deserunt" on npm](https://www.npmjs.com/search?q=keywords:@lambrioanpm/rem-doloribus-deserunt).
