# PromQL Editor

This is a React editor component to help you write PromQL queries.

![Screenshot](screenshot.png?raw=true)

## Setup

There are two ways to use this:

### 1. Try it on your Prometheus host

Use this method to quickly see results.
You need the following tools on your host:

* Prometheus running on http://localhost:9090
* A recent version of `node`

Run the following commands:

```
# Clone the repo
git clone https://github.com/davkal/promeditor
# Install dependencies
cd promeditor
yarn install
# Run application
yarn start
```

This starts a webserver on your host that serves the application.
Access the application on your browser: http://localhost:3000

If your Prometheus is running on a different host, you need to adjust the `proxy` value in `package.json`.


### 2. Include it into your React application

1. Either clone this repo or add it as a submodule.

2. Make sure your React app has all dependencies installed that are listed in `package.json`'s `dependencies` section (best to copy from there to get the same modules versions).

3. Look at `src/App.js` for an example on how to include the editor field into your app.

### 3. Using Docker

Adjust Prometheus URL in [package.json](package.json) for your docker setup, for example:

```js
  "proxy": "http://prometheus:9090"
```

Build local image with provided [Dockerfile](Dockerfile)

```sh
docker build -t promeditor -f Dockerfile .
```

and then run container

```sh
docker run --interactive --tty --publish 3000:3000 promeditor
```

## API

TBD

## LICENSE

[Apache-2.0](LICENSE)
